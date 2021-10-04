
# generate with


This renders but des not run r codes:

	 R -e rmarkdown::render"('Docs4+MD+R.md',output_file='test.html')"
	 R -e rmarkdown::render"('Docs4+MD+R.md',output_file='test.pdf')"

This runs r codes and show iages:

	R  -e "library(knitr); knit('Docs4+MD+R.md')"
	Rscript -e "library(knitr); knit('Docs4+MD+R.md')"
	pandoc Docs4+MD+R.txt -t html5 -o test.pdf

others

	Rscript -e "library(knitr); knit('./Docs4+MD+R+book.Rnw')"
	#pdflatex Docs4+MS+R.tex

run

 	R CMD Sweave --pdf Docs4+MD+R+book.Rnw


# doc4 R demo

you might need in linux R to clean the environment:

	sudo apt-get  -u dist-upgrade

```{r}
4*222
```
another

```{r test-a, eval=TRUE}
my.dir <- getwd()
list.files(my.dir, recursive= TRUE)
strsplit('hello world', ' ')
```

In R also installing the dependencies ‘stringi’, ‘stringr’ ‘digest’, ‘rlang’ htmltools withr rmd vs. rnw
	sudo apt-get install software-properties-common
	apt install --no-install-recommends software-properties-common dirmngr

	sudo add-apt-repository ppa:ubuntu-toolchain-r/test
	https://www.tuxamito.com/wiki/index.php/Installing_newer_GCC_versions_in_Ubuntu
	sudo apt-get install libfontconfig1-dev gcc-8 g++-8
	sudo update-alternatives --remove-all gcc
	sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 90 --slave /usr/bin/g++ g++ /usr/bin/g++-8
	sudo ulimit -s 16384     && sudo R -e 'install.packages("stringi");'
	conda install -c conda-forge r-bookdown

```{r setup, include=FALSE, eval=FALSE}
install.packages("stringi")
install.packages("bookdown")
install.packages("withr")
install.packages("knitr")
knitr::write_bib(x = c("knitr") , file = "test.bib")
```

remember some R versioning issues on R 3.2 cannot run, after R4 then install.packages("rmarkdown", dep = TRUE)
rmarkdown::pandoc_version()  nor knitr::write_bib(x = c("knitr", "rmarkdown") , file = "test.bib")

with bash

```{bash, engine.opts='-l'}
echo $PATH
```

# Vars

|                        | --variable        | --metadata        | YAML metadata and --metadata-file |
|------------------------|-------------------|-------------------|-----------------------------------|
| values can be…         | strings and bools | strings and bools | also YAML objects and lists       |
| strings are…           | inserted verbatim | escaped           | interpreted as markdown           |
| accessible by filters: | no                | yes               | yes                               |


Figures and tables with captions will be placed in `figure` and `table` environments, respectively.

```{r nice-fig, fig.cap='Here is a nice figure!', out.width='80%', fig.asp=.75, fig.align='center'}
par(mar = c(4, 4, .1, .1))
plot(pressure, type = 'b', pch = 19)
```

 (note, not all refs render as Figure \@ref(fig:nice-fig) or [@fig:nice-fig]  [@sec:others] )

can write citations, too. For example, we are using the **bookdown** package [@R-bookdown] using R Markdown and **knitr**


# Others {#otr}

```{r fig2, echo=FALSE}
library(ggplot2)
download.file(url = "https://ndownloader.figshare.com/files/7010681",  destfile = "data")
precip <- read.csv(file="data")
head(precip)
precip$DATE
qplot(x=precip$DATE,      y=precip$PRECIP)
```              

and


```{r results = 'asis', out.width="40px"}
download.file(url = "https://octodex.github.com/images/bannekat.png",
          destfile = "image.png",
          mode = 'wb')
knitr::include_graphics(path = "image.png") #to html  figure/Docs2-img.eps")
```

---
title: "Docs4 R Markdown Demos: Plot PDF ..."
output: pdf_document
---
