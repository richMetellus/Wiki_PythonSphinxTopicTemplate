# Sphinx Documentation Template

This is a very useful template I used for creating documentation using
python sphinx.

## Get Started

You only need to install `python` and install `pipenv` as the initial requirements.

1. Install python and `pip`
2. Then use `pip` to install `pipenv`

Once these two are install. To build the document you need to run the following commands

1. Start a virtual environment and install the python packages:

    ```python
    pipenv shell
    pipenv install
    ```

2. then build the document: open a terminal at the root folder of the document
   and then type the following command to build a live document

    ```python
    make livehtml
    ```

For more information, see the file `source/index.rst`.
