# Terminology

By now, you should have realized that the terminology used in prior discussions is rather verbose. This is because, in the current literature, there is a rather confusing mix of overlapping names:

- {term}`CAI` - Computer-Assisted Intervention
- {term}`CAS` - Computer-Assisted Surgery
- {term}`IGI` - Image-Guided Intervention
- {term}`IGS` - Image-Guided Surgery
- {term}`IGT` - Image-Guided Therapy

[comment]: <> (<cite>`GGC+2020`)
While [](https://doi.org/10.1097/AS9.0000000000000021) has attempted to provide a unified discussion surrounding these terms, their definitions have not been widely adopted (yet).

## Why the Confusion?

The terminology confusion arises because {term}`CAS` is inherently multidisciplinary. Each sub-discipline developed its own terminology during the field's early development, resulting in overlapping and sometimes conflicting terms.

Healthcare is provided by a multidisciplinary teams of health professional, in stages, at different part of a hospital system. Concretely, prior to a surgery, the patient is subject to an array of pre-surgical medical imaging scans for the purpose of diagnosis. These medical scans, including but not limited to {term}`CT` and {term}`MRI`, are operformed in an radiolgy suite by imaging technicians and radiologists.

Healthcare is provided by multidisciplinary teams of health professionals in stages across different parts of a hospital system. Prior to surgery, patients undergo an array of pre-surgical medical imaging scans for diagnosis. These medical scans, including but not limited to {term}`CT` and {term}`MRI`, are performed in a radiology suite by imaging technologists and radiologists. It should be noted that these pre-surgical imaging modalities *typically* cannot be acquired in real-time: the image acquisition may take minutes to hours, with computational post-processing (e.g. image formation/reconstruction) that requires additional time. This is in contrast to real-time imaging modalities such as {term}`US` and X-ray fluoroscopy, where images are visualized as soon as they are acquired.

```{figure} https://upload.wikimedia.org/wikipedia/commons/7/74/IMRI_suite.jpg
:label: fig_IR_suite
:alt: A depiction of an interventional radiology suite
:align: center
:width: 80%

An interventional radiology suite where biopsy, diagnosis or therapies are precisely guided with real-time fluoroscopy. Image courtesy via Wikimedia commons, accessed [here](https://commons.wikimedia.org/wiki/File:IMRI_suite.jpg) on 2026-01-03.
```

Based on the acquired medical imaging, hence the term **image-guided**, a treatment plan is formulated — for example, to identify the location of a tumour seated in deep tissues and determine the optimal trajectory for inserting an ablation applicator percutaneously. Such interventions can be performed by interventional radiologists in an interventional radiology ({term}`IR`) suite, hence the term **image-guided interventions** ({term}`IGI`).

```{figure} https://upload.wikimedia.org/wikipedia/commons/e/e6/Radiofrequency_ablation.jpg
:label: fig_RFA_Percutaneous
:alt: Tissue ablation using radiofrequency
:align: center
:width: 80%

A depiction of an ultrasound-guided, percutaneous liver tumour ablation using radiofrequency. Image courtesy via Wikimedia commons, accessed [here](https://commons.wikimedia.org/wiki/File:IMRI_suite.jpg) on 2026-01-03.
```

Surgery involves the dissection of tissues to access surgical targets and the joining of tissues to facilitate healing. Surgery is performed in the operating room ({term}`OR`) by teams of medical specialists, including surgeons, anesthesiologists, nurses, and technologists. Unlike diagnostic imaging suites, a typical {term}`OR` is **not** equipped with medical imaging modalities, although mobile {term}`US` or C-arm fluoroscopy may be utilized for intraoperative imaging.

```{figure} ./../images/fig_OR.jpg
:label: fig_Operating_room
:alt: A depiction of an operating room
:align: center
:width: 80%

A typical operating room with a teams of medical professionals, image courtesy of Prof. Matt Clarkson at UCL.
```

A [hybrid operating room](wiki:Hybrid_operating_room) is a surgical theatre equipped with advanced medical imaging modalities such as floor-mounted C-arm fluoroscopy, {term}`CT`, or {term}`MRI`. These systems enable {term}`MIS`, which minimizes surgical trauma and incision size. {term}`MIS` procedures are typically performed percutaneously, guided by real-time imaging from fluoroscopy, {term}`US`, or intraoperative 3D imaging such as [intraoperative MRI](wiki:Intraoperative_MRI) ({term}`iMRI`).


```{figure} https://upload.wikimedia.org/wikipedia/commons/0/07/Hybrid_operating_theatre_gemelli_rome.jpg
:label: fig_Operating_room_hybrid
:alt: A depiction of a hybrid operating room
:align: center
:width: 80%

A hybrid operating room with medical imaging modalities and computing resources. Image courtesy via Wikimedia commons, accessed [here](https://commons.wikimedia.org/wiki/File:Hybrid_operating_theatre_gemelli_rome.jpg) on 2026-01-03.
```

## Nomenclature

For the purpose of this course, let's adopt the following nomenclature:
- **Surgery**: the act of providing access to surgical targets; a procedure involving cutting and joining a patient's tissues
- **Therapy**: the act of treating a medical condition, e.g., radiofrequency ablation ({term}`RFA`) of a tumour, drug-eluting beads/stents, etc.
- **Interventions**: the broader term that encompasses **both** surgery and therapy
- **Computer-Assisted**: the use of computational methods in addition to imaging systems
- **Minimally Invasive**: limited incision size

Using this nomenclature, you should be able to describe, in concise terms, what {term}`CAS`, {term}`CAI`, {term}`IGI`, {term}`IGS`, {term}`IGT`, and {term}`MIS` mean.