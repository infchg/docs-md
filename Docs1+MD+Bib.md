

# Documents+BIB references, Docs1+MD+Bib.md 

The following 2-3 lines validate how we document using bib references: such as proceedings [@ndm06]
or published searches [@iaea], or other bibliography [@quickrender]



## Rendering commands


To convert .MD with bibliography in .PDF or HTML use:
```{bash}
pandoc -C  Docs1+MD+Bib.md -M link-citations  -o  outputs/Docs1+MD+Bib.pdf # easy with links
pandoc  Docs1+MD+Bib.md -o  outputs/Docs1+MD+Bib.pdf
pandoc --citeproc  Docs1+MD+Bib.md --metadata link-citations -o k.htm
pandoc --citeproc --bibliography md-bib2.bib Docs1+MD+Bib.md -t markdown-citations |pandoc - -o k.pdf
pandoc --citeproc  Docs1+MD+Bib.md -M link-citations  -o k.pdf   # With PDF Links !
pandoc --citeproc  Docs1+MD+Bib.md --metadata link-citations -t markdown-citations --wrap=none
```

if wished to render via Context  you would use instead:

	pandoc -D context > mycontext.tex
	pandoc --citeproc  Docs1+MD+Bib.md -t context  --template=mycontext.tex   -o k.tex
	mtxrun -result=pdf --script context  k.tex


## CSL vs BIB

Among two possible techniques to produce bibliographic references: 
 - CSL files (with the --csl setting) 
 - or Latex citations (with the --biblatex or --natbib settings).
 
remember, in some environments natbib wont create the references.
 

Could also use BIB Tex with 5 lines:
    pandoc -s --bibliography=foo.bib --biblatex -o foo.tex foo.md
	pdflatex foo.tex
	bibtex foo.aux
	pdflatex foo.tex
	pdflatex foo.tex



for Tex Include hyperref package into your document preamble or template with usepackage{hyperref} and all needed
```{bash}
	pandoc -D latex > mytemplate.tex
	pandoc --citeproc --bibliography md-bib2.bib Docs1+MD+Bib.md  --template=mytemplate.tex   -o k.tex
	pdflatex k.tex  --shell-escape 

\documentclass{article}
	%Include hyperref package into your document preamble using the command documentclass[smallextended]{svjour3}       % onecolumn (second format)
	usepackage{hyperref}
	 
```
 


[]: comments


remember, on latex we have        -D latex, --print-default-template=FORMAT to
Print the system default template for an output FORMAT.  (See -t for a list of possible FORMATs.) Templates in the user
data directory are ignored.  This option may be used with -o/--output to redirect output to  a  file,  but  -o/--output
must come before --print-default-template on the command line.


When using -t markdown-citationsNote, you  might need re-processing into more basic like:
```
    [2](#ref-R-rmarkdown) or [[2]]
    1. <a id=ref-R-knitr/>  auth titl journ
    ###### auth titl journ bib1 € {e1}

```
 

## Usefull latest 2021 software


usefull to have R & MD view (install using via apt dnf or AUR if you’re using an Arch-based Linux,
 - Remarkable V1.87,
 - **ReText** -  Atom.io
 - pip install grip
 * deb: libcurl4-openssl-dev (Debian, Ubuntu, etc)
 * rpm: libcurl-devel (Fedora, CentOS, RHEL)
 * csw: libcurl_dev (Solaris)


other installation commands
```{bash}
	#2021updata from OLD?? pandoc 1.16.0.2
	sudo dpkg -i pandoc-2.14.1-1-amd64.deb
	#Unpacking pandoc (2.14.1-1) over (1.16.0.2~dfsg-1) ...

	#2021 apt search iftex # to detect flavors
	sudo apt install texlive-generic-extra
```




# References & Biblio listed here


::: {#refs}
:::
 
	
	
# Annex

We can use annex after Refs thanks to the special ::: above (otherwise Refs come last). MD Doc examples:	git clone https://github.com/infchg/docs-md  , see [@md21]   Docs1+MD+Bib.md & bib & utf Docs2+Tex.tex    Docs3+MD+utf.md    Docs4+MD+R.md  


---
output: pdf_document
linkcolor: NavyBlue 
filecolor: yellow
citecolor: red
urlcolor: magenta
toccolor: cyan

bibliography: Docs1+MD+Bib.bib
csl: ieee.csl
NOheader-includes:
 - \usepackage[utf8]{inputenc}
 - \DeclareUnicodeCharacter{2208}{  \ensuremath{\in} } % 
---


