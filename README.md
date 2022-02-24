# jupyter-book-TAILOR-D3.2
TAILOR D3.2 - Handbook on Trustworthy AI

Basic Instuction for contributing in jupyter-book-TAILOR-D3.2 (Francesca Pratesi)

For Task Member: please, ask to your Task Leader how you can contribute in this Encyclopedia, and in which entries.

For Task Leader:
1) There is a folder for each task, where all the entries of that task are collected, plus a "index" folder that contains all the entries of the Encypedia.
Ideally, you should work in your folder only, while I'll take care of the index (but I'll ask you to double check the entries)

2) Please define the structure of your entries, indicating the hierarchy. E.g.,:
L1. Explainability
    L2. Dimensions
        L3. Model Specific vs Model Agnostic
        L3. Global vs Local explanations
    L2. Evaluating Explainations
...
I will take care to create a file in your folder and to add the entry to the Table of Content

3) Create a shared document for each entry, in the format which is more suitable for the corrispondent working group, i.e., word/openOffice/drive or LaTeX or the markup language used in the Jupyter Book (md). The you should write and refine the content of the entry.

4) Once the entry is complete, you should take care of the translation in the .md format (only if it is necessary, of course). Especially starting from .tex sources should not be too difficult, having also some examples and (at least at the moment) no code or table or other complex structures. There is also a tool (https://pandoc.org/) to convert LaTeX in markdown documents. However, I can help you in this process.

5) Put the content of the entry in the appropriate file (instruction for the writing, the compiling, and the publication are below)

#####################################################################################################################################################################
#                                                                                                                                                                   #
#               A guide to undestand the syntax of the Jupyter Book markdown language can be found here: https://jupyterbook.org/intro.html                         #
#                                                                                                                                                                   #
#####################################################################################################################################################################

For contributing in the git repository, only the first time:
- checkout the jupiter-book-TAILOR-D3.2 (all the git commands are the usual ones)
- install Jupyter Book, via pip (pip install -U jupyter-book) or via conda-forge (conda install -c conda-forge jupyter-book)
- install ghp-import: pip install ghp-import or sudo apt-get install ghp-import

All the git commands are the usual ones. Please consider that you should act only in the "main" branch; the other branch ("gh-pages") is automatically rewrote each time.

To compile the book (in the jupiter-book-TAILOR-D3.2 folder) execute:
jupyter-book build D3.2_Handbook_on_Trustworthy_AI
- if you can see all the editings, try to remove the _build folder
- at this point, you have the website in your local machine
- you can open _build/html/index.html to see the output
- once you finished the local editing, push the result in the git repository

Then, for updating the gh-pages branch and publishing the webpages, execute:
ghp-import -n -p -f D3.2_Handbook_on_Trustworthy_AI/_build/html
- wait from 1 to 10 minutes to see the results
