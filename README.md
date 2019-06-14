# A Parser That Adds Special Identifiers To Markdown Files For Deep Learning

GitHub contains a large corpus data that is amenable for NLP, in the form of Issues, READMEs, pull request comments and other items. However, this text is often accompanies by markdown which allows the user to specify styling (bold, underline, headings) and specialized formatting (code blocks, tables, block quotes, hyperlinks).  This library has two goals:

## 1. Insert custom field indicators

This is so markdown information is not lost.  For example, a list block is enclosed with `xxxlistB` and `xxxlistE` and a code block is enclosed with `xxxcdb` and `xxxcde`.  

## 2. Discard superflous information

Documentation TBD
