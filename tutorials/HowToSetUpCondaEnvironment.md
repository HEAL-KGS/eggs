How To Set Up Conda Environment


Make sure you’re in the correct directory.

1. Create a conda environment

```bash
conda create -n eggs python=3.10
```

1. Activate the newly created environment

```bash
conda activate eggs
```

1. Install various common packages that you might use

```bash
conda install scipy pandas scikit-learn seaborn shapely xarray dask netCDF4 bottleneck rasterio rioxarray
conda install jupyter
conda install -c conda-forge geopandas
```

### Accessing conda environments from Jupyter notebooks

---

At this point, you should be able to start a Jupyter session and open a notebook using the default kernel. However, your kernel list will only show the current environment.

Often, it’s necessary to switch between kernels from Jupyter directly so that we can access specific packages (or versions) installed in our various conda environments.

**Registering a single environment.**

The first option is to register a specific environment individually. This can be handy if you have several environments and want to keep your kernel list clean, as you can register and deregister environments as you like.

1. In your conda environment (e.g. `eggs`), install `ipykernel`
    
    ```bash
    (eggs)$ conda install ipykernel
    ```
    
2. Register the kernel spec with Jupyter using the following command.
    
    ```bash
    (eggs)$ ipython kernel install --user --name=eggs
    ```
    
    or
    
    ```bash
    (eggs) $ python -m ipykernel install --user --name=eggs
    ```
    
3. Now `eggs` will be displayed in your list of kernels on Jupyter (no need to restart, just refresh the page).
4. If you want to de-register the kernel spec, use the following:

```bash
$ jupyter kernelspec uninstall eggs
```