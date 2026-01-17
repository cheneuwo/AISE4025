# AISE 4025 at Western University, Canada

The website is live [here](https://cheneuwo.github.io/AISE4025/)

Updated on January 17, 2026

This work is built using [Jupyter Book 2](https://jupyterbook.org/stable/). To run it, JupyterBook V2 must be installed. Refer to [this page](https://jupyterbook.org/stable/get-started/install/) for installation process. 

In Anaconda, this can be accomplished using

```
conda install conda-forge::jupyter-book
```

To build a PDF version of this document, [typst](https://typst.app/) must be installed

```
conda install conda-forge::typst
```

The PDF can then be build:

```
jupyter book build --pdf
```

However, there seemed to be some compatibility issues in converting typst to PDF at the moment.

To build bibliography automatically, [myst](https://mystmd.org/) must be installed

```
conda install conda-forge::mystmd
```