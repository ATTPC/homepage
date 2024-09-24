# homepage

The homepage for the AT-TPC written using MkDocs

## Requirements

Python 3.8+

## Download and Install Dependencies

To setup this repository, first download it from GitHub using 

```bash
git clone https://github.com/ATTPC/homepage.git -b your_dev
``` 

where `your_dev` should be replaced with the name of your specific development branch. Then, from within your repository, create a virtual environment using

```bash
python -m venv .venv
```

You may need to replace `python` with a specific version such as `python3` or `python3.11`. Then activate your environment using

```bash
source .venv/bin/activate
```

Finally, install the dependencies using pip

```bash
pip install -r requirements.txt
```

Note: these instructions are for MacOS and Linux. Windows instructions are similar, but the commands will be slightly different.

## Run the website locally

To run a test of the website use the following command from the root of the repository

```bash
mkdocs serve
```

This will build and serve the website on localhost. MkDocs will watch for changes in the repo and update the site when files are changed.

## How to edit

Simply modify the existing MarkDown files in `docs` or add new ones! When adding a new file be sure to add it to the `nav` section of the `mkdocs.yml` file in the root of the repository.

## Deploying (Admin Only)

Clone both this repository and the Pages repo. From the Pages repo run the following command:

```bash
mkdocs gh-deploy --config-file <path_to_homepage>/mkdocs.yml --remote-branch master
```

Replace `<path_to_homepage>` with the path to this repository from the Pages repo. 