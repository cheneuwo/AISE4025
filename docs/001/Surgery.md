# Surgery

Before diving into the concept of computer-assisted surgery, we need to make a philosophical distinction that will guide our understanding throughout this course: the difference between **Surgery** and **Intervention**.

## But What Is Surgery?

According to the Oxford English Dictionary, the definition of the word [**Surgery**](https://www.oed.com/dictionary/surgery_n?tab=meaning_and_use#19777282) includes, among others:
- The art or practice of treating wounds, fractured bones, and other conditions by manual operation or instrumental appliances; surgical treatment
- Surgery of Access

These definitions reveal something important: surgery is fundamentally about **access** -- creating pathways to reach surgical targets that would otherwise be inaccessible. Consider a [hepatectomy](https://my.clevelandclinic.org/health/treatments/22930-hepatectomy-liver-resection) procedure as an example. Possible surgical approaches include:

> If you're having open surgery, your surgeon will make one long incision across your abdomen to open your abdominal cavity. If you're having laparoscopic surgery, your surgeon will make 4 to 6 "keyhole" incisions, which they'll use to place the camera (laparoscope) and surgical instruments to do the operation.

Both approaches are focused entirely on access, providing two essential elements: **visualization** (so surgeons can see the target, via direct human vision or indirect medical imaging) and **manipulation** (so surgeons can reach the surgical target with instruments).

## The Evolution of Surgical Access

Traditional open surgery requires large incisions to establish direct line-of-sight visualization (i.e., direct human vision) and unrestricted surgical instrument access.

```{figure} ./../images/1-s2.0-S1878788611001445-fx3.jpg
:label: fig_open_liver_surgery
:alt: A depiction of open liver surgery
:align: center
:width: 80%

A depiction of open liver surgery with large incision, image courtesy of {cite}`GG2011`.
```

However, advances in medical imaging and mechatronics have revolutionized this approach. Technologies such as laparoscopic cameras, fibre-optic illumination, miniaturized instruments, and medical robotics now enable surgeons to achieve nearly equivalent visualization and manipulation through small *keyhole* incisions, forming the foundation of **minimally invasive surgery**.

```{figure} ./../images/464_2022_9312_Fig9_HTML.webp
:label: fig_lapar_liver_surgery
:alt: A depiction of laparoscopic liver surgery
:align: center
:width: 80%

A depiction of minimally invasive surgery where surgical access is provided through trocar, image courtesy of citation {cite}`HXQ+2022`.
```

From an engineering perspective, this evolution represents an optimization problem: how do we maintain surgical capability while minimizing tissue trauma? The answer lies in advancing medical imaging systems, precision mechanics and mechatronics, and human-computer interfaces that extend the surgeon's sensory and motor capabilities.

## Surgery vs. Intervention: The Critical Distinction

In this course, we therefore make the critical distinction between **surgery** and **intervention**:

**Surgery** = The means of providing surgical **access** to anatomical targets (e.g. exposing a tumour hidden beneath organ surfaces), and

**Intervention** = The therapeutic act that directly improves the patient's condition (e.g. removing the tumour via resection or destroying it via thermal ablation).

This distinction appears across all surgical specialties:
- **Cardiac surgery**: sternotomy (*surgery*) enables heart valve replacement (*intervention*)
- **Neurosurgery**: craniotomy (*surgery*) enables brain tumour resection (*intervention*)
- **Orthopaedics**: arthroscopy (*surgery*) enables meniscus repairs (*intervention*)

## Implications for Computer-Assisted Surgery

This framework has profound implications for how we approach computer-assisted surgery technologies:

**Navigation and Guidance Systems** primarily assist with the surgical component - helping surgeons plan optimal access routes, tracking instrument positions, and navigate safely to targets while avoiding critical structures.

**Robotic Systems** can enhance both components - providing tremor-free access through constrained space (surgery) while enabling precise manipulation during the actual therapeutic interventions.

**Imaging Technologies** serve both functions - preoperative imaging modalities guide surgical planning and access, while intraoperative imaging modalities monitor the intervention itself.

## The Philosophical Insight
Understanding this distinction between **surgery** and **intervention** leads to the following realization: **surgery is, in fact, a side-effect of therapy!**

The research problem we wish to address, in this regard, is how to deliver therapeutic interventions without any, or minimal, surgical trauma to the patient. Every incision or every tissue manipulation represents a necessary compromise - a **side-effect** we accept to enable outcome-improving interventions.

This perspective explains why computer-assisted surgery technologies are so compelling: they promise to minimize the surgical side-effects while maximizing therapeutic precision. As biomedical engineers, our goal is not just to make surgery more precise, but to make it less necessary—to find ways to deliver therapeutic interventions with minimal surgical trauma.

This conceptual framework will guide our exploration of image-guided surgery, robotic systems, and emerging technologies that continue to push the boundaries of what's possible in minimally invasive intervention.