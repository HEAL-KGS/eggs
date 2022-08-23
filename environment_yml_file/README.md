# How to use the eggs_env.yml file to create an EGGS-tailored conda environment:
    1. Download eggs_env.yml to your operating system (OS). 
    2. Move it so that it has a filepath of C:\Users\YOUR-OS-NAME
    3. Open up your terminal/command prompt and activate your base environment    (conda activate base)
    4. When you see (base) at the very far left in your terminal, you can proceed to create the environment for EGGS.
    5. Create the environment using the .yml file that you downloaded.
    (conda env create -n ENVNAME --file eggs_env.yml)
    6. Hooray! Now all of the necessary packages to reproduce and run the scripts in this GitHub are downloaded. If any packages did not 
    download using this method, you could easily download them using: conda install --channel conda-forge PACKAGENAME
# Happy coding!
