# jupyterlab-cheatsheet

## Kernels

### Show all kernels
* `jupyter kernelspec list`

### Install new kernel
* `conda activate py36`
* `python -m ipykernel install --name py36`
   * installs kernel into shared location
*  `python -m ipykernel install --name py36 --user`
   * installs kernel into user location
* `conda deactivate`

### Uninstal kernelL
* `jupyter kernelspec uninstall py36`

## Cleanup after Jupyterlab installation

* `jupyter lab clean`
* `jlpm cache clean`
* `npm cache clean --force`

## Useful Jupyterlab extensions

### HTML_TOC support
* `conda install -c conda-forge jupyter_contrib_nbextensions`
* `conda install -c conda-forge "nbconvert=5.6.1"`
  * Fix of incompatible nbconvert >= 6

### NodeJS
* `conda install -c conda-forge nodejs`
  * Required by all extensions

### TOC extension
* `jupyter labextension install @jupyterlab/toc`
  * from Jupterlab 3.0 it is integral part of JupyterLab

### Plotly
[Getting started link](https://plot.ly/python/getting-started/)
* `conda install "ipywidgets>=7.5"`
* `jupyter labextension install jupyterlab-plotly`
  * JupyterLab renderer support
* `jupyter labextension install @jupyter-widgets/jupyterlab-manager plotlywidget`
  * Optional: Jupyter widgets extension
* `jupyter lab build`
* `jupyter lab clean`

## How to update extensions

* `jupyter labextension update @jupyter-widgets/jupyterlab-manager --no-build`
* `jupyter labextension update jupyterlab-plotly --no-build`
* `jupyter labextension update plotlywidget --no-build`
* `jupyter labextension update @jupyterlab/toc --no-build`
* `jupyter lab build`
* `jupyter lab clean`


## Keyboard shortcuts

```javascript
{
    "shortcuts": [

        // Restart kernel and run all cells
        {
            "command": "runmenu:restart-and-run-all",
            "keys": [
               "Ctrl Shift Enter"
            ],
            "selector": "[data-jp-code-runner]"
        },

        // Collapse all code
        {
            "command": "notebook:hide-all-cell-code",
            "keys": [
                "Ctrl + Shift + O"
            ],
            "selector": ".jp-Notebook:focus"
        },

        // Expand all code
        {
            "command": "notebook:show-all-cell-code",
            "keys": [
                "Ctrl + Shift + P"
            ],
            "selector": ".jp-Notebook:focus"
        }
    ]
}
```
