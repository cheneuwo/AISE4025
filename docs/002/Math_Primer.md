# Math Primer

## Cartesian Coordinates and Vector Geometry
Linear algebra, particularly Cartesian coordinate systems and vector geometry, is fundamental to {term}`CAS`. 
To explain why they are essential to all aspects of {term}`CAS`, let's begin with something familiar: a (medical) image:

```{figure} https://cancerquest.org/sites/default/files/2020-04/Ultrasound/IMG_0288.jpg
:label: fig_US_Liver_Tumours
:alt: A ultrasound image of liver with metastatic cancer growths
:align: center
:width: 80%

An ultrasound image of a liver containing metastatic cancer growths, image courtesy [here](https://cancerquest.org/patients/detection-and-diagnosis/ultrasound), accessed on January 6, 2026.
```

## From Pixels to Positions: Why We Need Coordinates

Consider an {term}`US` image of a patient's liver. Displayed on a computer monitor as a {term}`2D' image of different gray scale, different shades of gray represents different tissues types (often highlighted by tissue boundraries). In [](#fig_US_Liver_Tumours) for example, a tumour appears as a darker region within the brighter liver parenchyma. But how does one infer the size and location of a tumour based on an image?

Using a digital computer, a grey-scale image is represented as a **{term}`2D` matrix** of numerical values. Each element in this matrix represents a *pixel*, and the numerical value at each position (pixel) encodes the tissue's appearance in terms of pixel intensity. For example, [](#fig_US_Liver_Tumours) is an image of $245 \times 245$ pixels stored as a matrix:

$$
I = \begin{bmatrix}
I_{0,0} & I_{0,1} & \cdots & I_{0,244} \\
I_{1,0} & I_{1,1} & \cdots & I_{1,244} \\
\vdots & \vdots & \ddots & \vdots \\
I_{244,0} & I_{245,1} & \cdots & I_{244,244}
\end{bmatrix}
$$

where each $I_{i,j}$ represents the intensity value at row $i$ and column $j$. Each pixel in an {term}`US` image is typically represented using a 8-bit of storage (e.g. 1-byte) with the pixel intensity value ranging from $0$ to $255$, where $I_{i,j}=0$ is pure black and $I_{i,j}=255$ is pure white.

```{figure} ./../images/002/fig_image_coordinate.png
:label: fig_US_Liver_Tumours_coord
:alt: A coordinate system assited to an image
:align: center
:width: 80%

A coordinate system assigned to an US image, where the top-left corner is *arbitrary* designated as the origin. A pixel at location $(x,y)$ with an intensity value $v$ is thus referred to as $I(x,y)=v$, image modified based on the image courtesy [here](https://cancerquest.org/patients/detection-and-diagnosis/ultrasound), accessed on January 6, 2026.
```

That is, each pixel in a {term}`2D` image is referred by $(x,y)$ position, which is also the index to the {term}`2D` matrix that is used to store and represent this image in a computer system. The $(x,y)$ location also represents a vector from the origin of the coordinate system $(0,0)$.

### The Challenge: From Image Indices to Physical Space

Suppose a radiologist examines this {term}`US` image and identifies that one of the tumour centre appears at pixel location $(66,110)$ in the image. The logical questions that follow are:
1. **Where is this location in the patient's body**? This matrix indices $(66,110)$ does not indicate anything about the physical location of it with respect to the patient.
1. **What about the physical size of the tumour**? The {term}`2D` matrix, by itself, does not have any information about the physical scale of the image. That is, how do we convert pixel size to a physical unit such as in millimetre?
3. **How do one guide a surgical instrument to this location**? Suppose we want to insert a {term}`RFA` ablation application into this tumour, we need to relate this abstract pixel coordinate system into a physical location that a navigation system can use.

To answer these question requires an understanding of image presentation, coordinate systems, and **transformation** between coordinate systems. In this regard, a review of linear algebra and vector geometry is needed.

### Multi-Channel image and {term}`3D` Volumetric Data

While a {term}`2D` grey-scale image such as {term}`US` or X-ray image can be represented by {term}`2D` matrix in a digital system, color images and volumetric (i.e. {term}`3D`) data requires different representation.

For example, a colour image is typically represented as 3 {term}`2D` images, each {term}`2D` image correspond to a colour channel of red, green, and blue ({term}`RGB`) primary colours. Conceptually, these 3 {term}`2D` images can be stacked on top of each other, forming a {term}`2D` image but each pixel is a {term}`1D` vector of $3$ values (i.e. multi-channel).

```{figure} https://ars.els-cdn.com/content/image/3-s2.0-B9780128230145000077-f03-08-9780128230145.jpg
:label: fig_RGB
:alt: A conceptual representation of a 5x5 RGB colour image
:align: center
:width: 80%

A conceptual representation of a 5x5 RGB colour image, image courtesy [here](https://www.sciencedirect.com/topics/engineering/rgb-image), accessed on January 6, 2026.
```
A {term}`3D` volumetric image data such as {term}`CT` or {term}`MRI` are typically displayed, on a {term}`2D` monitor, as a series of {term}`2D` images:

```{figure} https://images.theconversation.com/files/423640/original/file-20210928-26-3rul6h.jpg?ixlib=rb-4.1.0&q=45&auto=format&w=754&h=503&fit=crop&dpr=1
:label: fig_CT_slices
:alt: CT slices
:align: center
:width: 80%

Sequential CT slices displayed as 2D images, image courtesy [here](https://theconversation.com/50-years-ago-the-first-ct-scan-let-doctors-see-inside-a-living-skull-thanks-to-an-eccentric-engineer-at-the-beatles-record-company-149907), accessed on January 6, 2026.
```
This was mainly done for historical reasons including the lack of computational power to render these volumetric data in {term}`3D` using technique such as <wiki:Volume_rendering>.

A volumetric data is presented digitally as {term}`3D` array in computer where, conceptually, each 2D slice is assigned a $x-y$ coordinate system and sequential images are stacked in the $z-$axis.
```{figure} ./../images/002/fig_3D_volume.png
:label: fig_3D_volume
:alt: A coordinate system assited to a 3D volume
:align: center
:width: 80%

A coordinate system assigned to a 3D volumetric data, where sequential 2D images are assigned a z-coordinate value.
```
In this regard, each **voxel** (i.e. a *volumetric* pixel) is indexed using the $(x,y,z)$ notation.

## Enter Cartesian Coordinate Systems

The solution begins with establishing a **Cartesian coordinate system**—a mathematical framework named after René Descartes that allows us to uniquely specify any point in space using numerical coordinates.

In 2D (for our image example), we define:
- An **origin** point (typically the top-left corner of the image, at pixel $(0,0)$),
- Two perpendicular **axes** (horizontal $x$-axis and vertical $y$-axis), and
- A **scale** that converts pixel indices to physical distances (e.g., each pixel represents 0.5 mm × 0.5 mm of actual tissue).

With this framework, we can now say that the tumour centre at pixel $(256, 300)$ corresponds to physical coordinates:

$$
\begin{aligned}
x &= 256 \times 0.5\text{ mm} = 128\text{ mm} \\
y &= 300 \times 0.5\text{ mm} = 150\text{ mm}
\end{aligned}
$$

measured from the origin of our chosen coordinate system.

## Vector Geometry: Describing Positions and Transformations

But we're not done yet. In surgical navigation, we need to work with:
- **Positions** of anatomical landmarks and surgical targets,
- **Directions** along which instruments should be inserted,
- **Distances** between critical structures,
- **Rotations** that account for different patient orientations, and
- **Transformations** that map coordinates between different reference frames.

All of these concepts are elegantly expressed using **vector geometry**. A vector is simply an ordered list of numbers that can represent:
- A position in space: $\mathbf{p} = \begin{bmatrix} x \\ y \\ z \end{bmatrix}$
- A direction and magnitude: $\mathbf{v} = \begin{bmatrix} v_x \\ v_y \\ v_z \end{bmatrix}$
- A displacement from one point to another

## The Road Ahead

In the sections that follow, we will systematically develop the mathematical tools needed for computer-assisted surgery:

1. **Cartesian Coordinate Systems**: Establishing reference frames for medical images and physical space
2. **Vectors and Vector Operations**: Representing positions, directions, and performing geometric calculations
3. **Coordinate Transformations**: Relating different reference frames (image space, patient space, instrument space)
4. **Homogeneous Coordinates**: A powerful framework for combining rotations, translations, and scaling
5. **Applications to Surgical Navigation**: Bringing these concepts together to solve real navigation problems

By the end of this mathematical foundation, you'll understand why every pixel in a medical image, every point on a patient's anatomy, and every position of a surgical instrument can be precisely described, manipulated, and related to one another through the elegant language of linear algebra.

Let's begin our journey into Cartesian coordinate systems.