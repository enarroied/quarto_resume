[![Built with Quarto](https://img.shields.io/badge/Built_with-Quarto-2196F3?style=flat&logo=quarto)](https://quarto.org)
[![Python 3.12](https://img.shields.io/badge/Python-3.12-3776AB?logo=python)](https://python.org)

# Quarto Résumé

My personal résumé, using Quarto and some other awesome libraries.

## Workflow

Built using these tools:

* [Quarto](https://quarto.org/) to create an HTML-based report
* [WeasyPrint](https://doc.courtbouillon.org/weasyprint/stable/index.html) (see on [PyPI](https://pypi.org/project/weasyprint/)) to render the HTML as PDF
* [Great-Tables](https://posit-dev.github.io/great-tables/) (see on [PyPI](https://pypi.org/project/great-tables/)) to create the side tables with the skills

While it's not a direct part of this project, I created the QR Code for the logo using [Segno](https://pypi.org/project/segno/).

To create the HTML file first, and the PDF file later, we need to type this in our CLI:

```bash
quarto render resume.qmd
weasyprint resume.html resume.pdf -s css/report_style.css
```

## Why use HTML + WeasyPrint

Quarto can generate PDF reports directly. The "problem" with this approach is that it uses LaTeX under the hood. If your résumé needs to look academic, you should *probably* use that option, and look at [projects like this one](https://github.com/schochastics/quarto-cv), or [plenty of others](https://github.com/mcanouil/awesome-quarto).

The approach I took has the following advantages (althought this may be subjective):

* It generates an HTML file (the HTML output deserves bigger fonts), it's an extra output we can use for a blog for example
* It allows emojis (LaTeX struggles with that)
* Great-Tables renders better in HTML format (in June of 2025)
* It uses CSS (LaTeX makes CSS enjoyable by comparison)

