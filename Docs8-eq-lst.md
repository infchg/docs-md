# Docs8

generate using:

		pandoc -N -F pandoc-crossref  --citeproc  -M link-citations  -M highlightjs=1 -t html5  Docs8-eq-lst.md
		pandoc -F pandoc-crossref  -t html5  Docs8-eq-lst.md


$$ S(x) = \int_{x_1}^{x_2} a x+b \ \mathrm{d}x $$ {#eq:eqn2}

refs are @eq:eqn2 and [@lst:cap; @lst:bas] ,

```{#lst:cap .haskell caption="Listing caption"}
main :: IO ()
main = putStrLn "Hello World!"
```
and

```{#lst:bas .bash caption="bash code"}
echo ls
```

#### Othernote1


##### Othernote2 {#nn}


###### Othernote3


a


a


a


## also without cross  
without cross could still use links  or [#lst:cap](#lst:cap)  or [#nn](#nn) to IDs
even in html <a href=#lst:cap>aa</a> <a href=#nn>aa</a> <a href=#Othernote1>aa</a>
or redefine [lis_cap] and [lis:cap]

	pandoc  -t html Docs8-eq-lst.md >tes.html


[lis_cap]:  #lst:cap
[lis:cap]:  #lst:cap
[comm]:  note the style can be at the end

<style>
li { color: darkblue }
strong { color: Orange }
h1{ color: DarkOrange }
del { color: Green  }
.sourceCode { color: Green  }
h2 { color: Green  }
em { color: blue } //ok
</style>
