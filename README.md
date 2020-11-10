# climate-downloads
This is a collection of scripts for downloading weather and climate data.

## Using these scripts
Each of these scripts downloads data from a specific weather or climate data product, while allowing temporal and geographic subsampling. Some scripts have built-in code for resampling (i.e. going from hourly to daily data). All scripts are Jupyter Notebooks running Python 3, and contain extra documentation on how to register for data access if needed, or on any other tools necessary to download the data. 

Use the `dwnld_config_template.py` file to input your own paths where you want your data to be saved. Save this file as `dwnld_config.py` (the new file will be ignored through the  `.gitignore` file). Currently, all files will be saved to a `[raw_data_dir]/[model or data product name]` directory (the subdirectory of which is created if it does not yet exist), which `[raw_data_dir]` set in the `config` file. 

Make sure you have all the relevant packages for each script installed. A future version of this repo may include a `conda` environment `yaml` file that specifies all of the packages used in these scripts.

## Coming soon
- TAMSAT
- observational sea surface temperature datasets (OISST, ERSST)
- CHIRPS
- CHIRTS

## Contributing 
Pull requests are welcome. I'd like for this to become a centralized resource, with easy-to-use code to download any commonly-used weather and climate data. However, I'd ask that you keep several aspects of the format for ease of use and generalizability:
- all final output files should be saved to `[raw_data_dir]/[model or data product name]`, with `[raw_data_dir]` set by each user in their `dwnld_config.py` file. The scripts should create the subdirectory if it does not yet exist.
- all final output files should be in NetCDF format
- all final output files should be in a one-file-per-variable format, with the variable in the file called the same as the `[variable shorthand]` in the filename (below)
- all final output files should follow CMIP5 naming conventions, i.e.: 

`[variable shorthand]_[data frequency]_[model or data product name]_[experiment or timeframe]_[run or other info]_[date in YYYYMMDD-YYYYMMDD format](_[file suffix with geographic information]).nc`

Furthermore, please document your code as well as you can. Additionally, when you can, add links to documentation on how to access the datasets, or any additional tools that are needed (for example, ECMWF's API). 

Eventually, I'd also like to put an `environment.yaml` file that keeps track of any of the packages used in these scripts as well.



