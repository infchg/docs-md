# Docs7

 filter recognizes code blocks with the .pyplot or .plotly classes  https://hackage.haskell.org/package/pandoc-pyplot

```{.pyplot}
import matplotlib.pyplot as plt

plt.figure()
plt.plot([0,1,2,3,4], [1,2,3,4,5])
plt.title('This is an example figure')
```

run with:
	sudo stack install pandoc-pyplot  #From Hackage/Stackage
	pandoc --filter pandoc-pyplot Docs7-pypl.md -o out.html
	pandoc --filter pandoc-pyplot Docs7-pypl.md -o out.pdf
	{#fig:myex .pyplot caption="fig caption" include=style.py}
