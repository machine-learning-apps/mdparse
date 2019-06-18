[![GitHub license](https://img.shields.io/github/license/machine-learning-apps/mdparse.svg)](https://github.com/machine-learning-apps/mdparse/blob/master/LICENSE) 
[![Python 3.7](https://img.shields.io/badge/python-3.7-blue.svg)](https://www.python.org/downloads/release/python-370/)
[![PyPI version](https://badge.fury.io/py/mdparse.svg)](https://badge.fury.io/py/mdparse)


# A Parser That Adds Special Identifiers To Markdown Files For Deep Learning

GitHub contains a large corpus data that is amenable for NLP, in the form of Issues, READMEs, pull request comments and other items. However, this text is often accompanies by markdown which allows the user to specify styling (bold, underline, headings) and specialized formatting (code blocks, tables, block quotes, hyperlinks).  This library has two goals:

## 1. Insert custom field indicators

This is so markdown information is not lost.  For example, a list block is enclosed with `xxxlistB` and `xxxlistE` and a code block is enclosed with `xxxcdb` and `xxxcde`.  Other noteable examples:

- @mentions:  xxxatmention  (the handle is removed and replaced by just this indicator)
- quote blocks: xxxqb/xxxqe
- strikethrough: xxxdelb/xxxdele
- horizontal rule: xxxhr
- {large, medium, small} headers: annotated with xxxh{l,m,s}.  H1=large, H2-3=medium, H4-6=small.


## 2. Discard superflous information

GitHub issues often contain a large stack trace, or a large table with data.  This library comes equipped with sensible defaults to surface the most relevant information and discard what would otherwhise be lots of characters for a machine learning algorithm to handle:

- Code Blocks: only first two and last two rows are kept 
- Tables:  only table headers are kept
- Urls:  only the host is kept.  For example www.google.com/search is reformatted to www.google.com
- Images: the image is discarded but the file extension and metadata about the image (available to screenreader) is extracted.
- IP Addresses, extremely long numbers are marked as xxunk


This parser works by converting markdown to HTML then converting the HTML (along with some of the HTML tags, in certain cases) to text.


# Installation

`pip install mdparse`

# Examples

See [/notebooks/Demo.ipynb](/notebooks/Demo.ipynb) for an example of the transformations this parser does on a markdown file:

<img src="https://github.com/machine-learning-apps/mdparse/blob/master/images/demo.png" width="739" height="1479">
