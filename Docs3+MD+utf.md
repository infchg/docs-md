

For UTF8 chars like  x â X  you might need extra headers or add in your tempalte
    pandoc --citeproc  md-bib1.md -M link-citations --template=mytemplate.tex  -o k.pdf   # With UTF Template
    pandoc -s --citeproc  md-bib1.md -M link-citations  --include-in-header utf8.tex  -o k.pdf   # with utf8 including:
    \DeclareUnicodeCharacter{2208}{  \ensuremath{\in}  } % 

