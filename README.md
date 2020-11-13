An example repo with .ipynb and linked .md files

Convert from .ipynb to .md:


    jupytext --to=md --output mtcars.md mtcars.ipynb

Inline code eval for markdown sections of the notebook requires

    pip install jupyter_contrib_nbextensions
    jupyter contrib nbextension install --user
    jupyter nbextension enable python-markdown/main

see: https://stackoverflow.com/a/52874352/1104685

