# conda-cheatsheet
Quick overview of most useful conda commands

## Show existing environments
* `conda env list`
* `conda info --envs`

## Create new environment
* `conda create -n py39 python=3.9`
  * Env with pure Python
* `conda create -n py39 python=3.9 -c conda-forge`
  * Env with pure Python from conda-forge
* `conda create -n py39 anaconda python=3.9`
  * Build environment with all Anaconda packages

## Install packages
* `conda install pandas`
* `conda install pandas==0.25`
  * Install specific version of library
* `conda install -c conda-forge pandas`
  * Install from conda-forge repository

## Update packages
* `conda update pandas`
* `conda update pandas --no-deps`
  * Update without updating all dependencies
* `conda update --all`
  * Update all packages in env

## Remove environment
* `conda remove -n py39 --all`

## Rename environment
* `conda rename -n old_env new_env`

## Export environment
* `conda env export  --no-builds > environment.yaml`

## Recreate env from export
* `conda env create -n my_env -f environment.yaml`

## Conda channels
* `conda config --show channels`
  * Show channels
* `conda config --add channels <channel-name>`
  * Add channel as first on the list
* `conda config --append channels <channel-name>`
  * Add channel as last on the list

## Update conda
* `conda update conda`
  * Updates conda in current environment
* `conda update -n base conda`
  * Updates conda in "base" environment


# How to make `conda` work behind firewall / proxy?

## Allow connectivity to public servers
```
*.pypi.org
*.pythonhosted.org
*.continuum.io
* anaconda.com
*.conda.io
*.github.com
*.githubusercontent.com
*.npmjs.com
*.yarnpkg.com
```

## Set PROXY server into system variables
* `set HTTP_PROXY=http://user:password@proxy.server.com:PORT`
* `set HTTPS_PROXY=https://user:password@proxy.server.com:PORT`

## conda
* `conda config --set ssl_verify False`
  * Disable SSL for conda

## pip
* `pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org pandas`
  * Trusted host does not require SSL
* `pip install --proxy=http://user:password@proxy.server.com:PORT pandas`
  * Install using defined proxy server
  
## npm
* Disables SSL
  * `npm set strict-ssl False`
* Set proxy for both http + https
  * `npm config set proxy http://user:password@proxy.server.com:PORT`
  * `npm config set proxy httpS://user:password@proxy.server.com:PORT`
* Set registry (optional)
  * `npm config set registry http://registry.npmjs`



