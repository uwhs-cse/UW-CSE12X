# UW CSE 12X Open Access Prototype

This is an open access website to host the University of Washington's CSE 12X series course materials.

## Usage

### Building the book

If you'd like to develop and/or build the UW CSE 12X Open Access Prototype book, you should:

1. Clone this repository
2. Run `pip install -r requirements.txt` (it is recommended you do this within a virtual environment)
3. (Optional) Edit the books source files located in the `uw-cse-12x-open-access-prototype/` directory
4. Run `jupyter-book clean UW-CSE12X/` to remove any existing builds
5. Run `jupyter-book build UW-CSE12X/`

A fully-rendered HTML version of the book will be built in `uw-cse-12x-open-access-prototype/_build/html/`.

### Hosting the book

Please see the [Jupyter Book documentation](https://jupyterbook.org/publish/web.html) to discover options for deploying a book online using services such as GitHub, GitLab, or Netlify.

For GitHub and GitLab deployment specifically, the [cookiecutter-jupyter-book](https://github.com/executablebooks/cookiecutter-jupyter-book) includes templates for, and information about, optional continuous integration (CI) workflow files to help easily and automatically deploy books online with GitHub or GitLab. For example, if you chose `github` for the `include_ci` cookiecutter option, your book template was created with a GitHub actions workflow file that, once pushed to GitHub, automatically renders and pushes your book to the `gh-pages` branch of your repo and hosts it on GitHub Pages when a push or pull request is made to the main branch.

Go to https://uwhs-cse.github.io/UW-CSE12X/index.html to view the Jupyter Book.