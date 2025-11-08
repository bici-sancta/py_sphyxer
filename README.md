### py_sphyxer

#### demo repo for sphinx documentation setup


sequence of commands to generate spinx docs ...

$ pip install sphinx

ensure directory structure:

py_sphyer
- data
- docs
- reports
- src
  - __init__.py
  - data
  - __init__.py
    - read_data.py
  - ticker
    - __init__.py
    - tkr.py
    - tkr_utils.py
  - models
    - __init__.py
    - base_model.py
    - arima.py
  - utils.py
- test

commands (from /docs directory)
user:py_sphyxers/docs$ sphinx-quickstart
- separate source and build directories: y

from project main directory
user:py_sphyxers$ sphinx-apidoc -o docs src

update /docs/source/conf.py

extensions = [
            'sphinx.ext.autodoc',
            'sphinx.ext.napoleon',
            'sphinx.ext.viewcode'
            ]
html_theme = 'sphinx_rtd_theme'

add elements to index.rst file, e.g.,:
   introduction
   usage
   examples
   src

from directory: project/docs ...
user:py_sphyxers/docs$ make html

to re-build after repo changes:
user:py_sphyxers/docs$ make clean
user:py_sphyxers/docs$ make html


how to make html viewable on github:
???


which files are necessary / unnecesaary to commit to the repo?
- docs/build/html - yes
- docs/build/doctrees - ?
- docs/source - ?
- docs/make.bat, Makefile, src.rst, src.data.rst, etc - ?