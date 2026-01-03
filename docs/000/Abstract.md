# Abstract
+++ {"part": "abstract"}
This is a work in progress. This document will be updated continuously.

This document is a collection of supplemental materials for AISE 4025, titled **Introduction to Computer-Assisted Surgery: Theory and Practice**, taught at the Department of Electrical and Computer Engineering at Western University, Canada.

January 1, 2026
+++

While this course focuses on Computer-Assisted Surgery ({term}`CAS`), let's begin our dialogue within the broader context of Computer-Integrated Interventional Medicine ({term}`CIIM`).

{term}`CIIM` is an interdisciplinary research field where computerized techniques are applied to every aspect of medical interventions. A close analogy is the design and manufacturing of an automobile: computer software is used in the creation, modification, analysis, and optimization of surgical approaches, and computer software and mechatronics are used to control and assist the execution of these surgical maneuvers. In other words, computer-integrated interventional medicine is the application of **Computer-Aided Design** ({term}`CAD`), **Computer-Aided Manufacturing** ({term}`CAM`), and **Total Quality Management** ({term}`TQM`) to interventional medicine.

```{figure} ./../images/I4M_Data_Flow.png
:label: fig_data_flow
:alt: Workflow of CAS
:align: center
:width: 80%

Image courtesy of [Dr. Russel Taylor](https://www.cs.jhu.edu/~rht/Research.html#VISION), accessed July 7, 2025.
```

## The Manufacturing Analogy in Clinical Practice
Just as modern automotive manufacturing transforms raw materials into precision vehicles through engineering processes, computer-integrated interventional medicine transforms diagnostic information into therapeutic outcomes:

**In Automotive Manufacturing**
- **{term}`CAD`**: Engineers create 3D models, run crash simulations, and optimize aerodynamics
- **{term}`CAM`**: Robotic assembly lines position components with sub-millimetre precision
- **{term}`TQM`**: Real-time sensors monitor quality, detect defects, and trigger corrections

**In Computer-Assisted Surgical Interventions**
- **{term}`CAD`**: Surgical planning. Surgeons create patient-specific plans that may include 3D models of patient anatomy, simulation of procedures, and optimization of surgical approaches
- **{term}`CAM`**: Surgical execution. Surgeons use advanced mechatronics such as surgical navigation systems or medical robotics to guide surgical instruments with sub-millimetre accuracy to surgical targets
- **{term}`TQM`**: Surgical assessment. Surgical outcomes are recorded, complications are identified, and used to improve future procedures

This analogy extends beyond superficial similarities - both domains require integration of design software, precision tools, and quality assurance systems to achieve consistent, high-quality outcomes.

In this regard, interventional medicine is treated, using engineering language, as a closed-loop process of:
1. Combining specific information about the patient with the physician's general knowledge to determine the patient's condition,
1. Formulating a plan of action,
1. Carrying out this plan, and
1. Evaluating the results has existed since ancient times.

These steps are, traditionally, all taken place in the physician's head: the ability of modern computer-based technology to assist humans in processing and acting on complex information will profoundly enhance this closed-loop process.

## What is Computer-Assisted Intervention ({term}`CAI`)

Interventional medicine typically takes place in three stages:

1. **Planning**: For any patient, we need to
   - Perform diagnosis: find out what is wrong. This is typically performed using aids from medical mechatronics (e.g. blood pressure monitor) and medical imaging (e.g. ultrasound and x-ray)
   - Formulate a course of treatment: for example, if a patient has a tumour in the liver, should it be surgically removed, undergo chemotherapy, or be treated with thermal or chemical ablation?
   - This **planning** stage corresponds to {term}`CAD`.
1. **Execution**: Once the plan is formulated, we need to ensure it is executed as planned. For example, if the course of treatment for a patient with liver tumour is thermal ablation, how do we place the ablation applicator at the intended location to ensure complete tumour necrosis?
   - This **execution** stage, when assisted using computerized methods, corresponds to computer-aided manufacturing (CAM).
1. **Quality Control**: How do we know if what was planned and executed was effective? Past outcomes can be analyzed to provide insight for further surgery; thus the **quality control** stage provides feedback for this closed-loop process of {term}`CAI`.

## Core Technology Pillars of {term}`CAI`
Computer-assisted intervention rests on three foundational technology pillars:

### Medical Imaging and Visualization
Modern interventional medicine relies heavily on our ability to "see inside" the patient:
- **Preoperative imaging** (X-ray, Computed Tomography ({term}`CT`), Magnetic Resonance Imaging ({term}`MRI`), and ultrasound ({term}`US`)) provides detailed anatomical information for surgical planning.
- **Intraoperative imaging** ({term}`US`, fluoroscopy) provides real-time updates during procedures,
- **Mixed-reality systems** overlays enhance the surgeon's view of the patient.

### Surgical Navigation
Akin to Global Positioning System ({term}`GPS`) for automotive navigation, surgical navigation systems track surgical instruments relative to patient anatomy:
- **Optical tracking systems ({term}`OTS`)** use cameras to track markers on the patient or surgical instruments,
- **Magnetic tracking systems ({term}`MTS`)** enable localization of both rigid and flexible surgical instruments,
- **Registration algorithms** align preoperative images with intraoperative reality,
- **Calibration algorithms** maintain accuracy throughout dynamic procedures.

### Robotics and Mechatronics
Robotic systems extend human capabilities in the operating room:
- **Master-slave systems** filter tremor and scale motions for microsurgery,
- **Haptic feedback devices** provide force sensation for remote manipulation,
- **Specialized end-effectors** perform tasks that are traditionally difficult for human operators to perform, and
- **Autonomous subsystems** handle routine tasks while surgeons focus on critical decisions.

This course focuses on {term}`CAS`, a subdiscipline of {term}`CIIM`. As an introductory course, we will explore the fundamental principles and technologies that underpin this rapidly evolving field. While we will develop a solid foundation in core concepts, from surgical metrology to image registration and system implementation, it is important to recognize that {term}`CIIM` remains an area of active research. New techniques, technologies, and clinical applications continue to emerge, making this an exciting time to enter the field. The knowledge and skills you acquire in this course will provide you with the essential tools to understand current systems and contribute to future innovations in {term}`CIIM`.