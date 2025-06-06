# Configuration file for the Sphinx documentation builder.
#
# For the full list of built-in configuration values, see the documentation:
# https://www.sphinx-doc.org/en/master/usage/configuration.html

# -- Project information -----------------------------------------------------
# https://www.sphinx-doc.org/en/master/usage/configuration.html#project-information

project = "Documentation Python"
copyright = "2025, Clément 'Carcinome' Aicardi"
author = "Clément 'Carcinome' Aicardi"
release = "alpha_v0.1"

# -- General configuration ---------------------------------------------------
# https://www.sphinx-doc.org/en/master/usage/configuration.html#general-configuration

extensions = [
    "sphinx.ext.autodoc",
    "sphinx.ext.viewcode",
    "sphinx_rtd_theme",  # Utilisation du thème RTD
]

templates_path = ["_templates"]
exclude_patterns = []

language = "fr"

# -- Options for HTML output -------------------------------------------------
# https://www.sphinx-doc.org/en/master/usage/configuration.html#options-for-html-output

html_theme = "sphinx_rtd_theme"
html_static_path = ["_static"]

# -- Options for LaTeX output ------------------------------------------------

latex_engine = "xelatex"  # Peut être changé en 'pdflatex' ou 'lualatex'

latex_elements = {
    "papersize": "a4paper",
    "pointsize": "10pt",
    "preamble": r"""
\usepackage{amsmath}
\usepackage{amssymb}
""",
}
