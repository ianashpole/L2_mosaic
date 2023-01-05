# L2_mosaic

Code and data for testing how to create a daily, gridded ("L3") field ("mosaic") from individual MODIS L2 swath files.
&nbsp;  
## Repository contents
This repository contains 3 ipython notebooks:
1. L2_mosaic_with_regrid_final.ipynb
    - a demonstration of a working method for creating the mosaic which seems to reproduce the results from ordering the same files via the laads find data interface with the "mosaic" post-processing option requested
        - (this code is necessary as it is not practical ordering a large number of files to be post-processed via laads)
2. nearest_neighbour_ri_testing.ipynb
    - a code snippet testing the regridding parameters used in #1
3. L2_mosaic_testing.ipynb
    - an initial test at mosaic creation that highlighted a problem with overlapping swaths
        
It also contains the following files:
- list_of_input_swath_files
    - this is a list of the files used in `L2_mosaic_with_regrid_final.ipynb`, which can be downloaded from laads
- MYDATML2.A2022214.mosaic.061.2022348060413.psmcrpcs_000501886006.Viewing_Zenith_10km.hdf
    - this is a file downloaded from the laads find data interface.
    - the files searched for are those specified in list_of_input_swath_files
    - the following post-processing options are applied:
        - mosaic: YES
        - reproject: YES
            - output pixel size = 0.1
            - projection = GEO
            - resample type = nearest
- example_images.pdf
    - some images created using the ipython codes above and also from plotting certain files in panoply
        - images included annotations for explanation
