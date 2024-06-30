---
title: A Script To Clear Data Sets In Adobe Illustrator
publishdate: 2024-06-30T07:36:20+02:00
tech: [js]
tags: [scripting]
draft: false
---

I use the [data merge feature in Illustrator](https://helpx.adobe.com/illustrator/using/data-driven-graphics-templates-variables.html) to mass generate certificates at work. You can upload your data as CSV or XML file though I'd recommend doing it through the [Variable Importer script](https://github.com/Silly-V/Adobe-Illustrator/tree/master/Dataset%20Processing).

As great as it is, one annoying thing is that it's hard to clear our the datasets as it makes you do it one by one. To do this, I had to create a script which just loops through the data sets and deletes them.

```js{aria-label="Clean Dataset Code"}
#target illustrator;
var doc = app.activeDocument;
for (var i=doc.dataSets.length-1; i >= 0 ; i--) {
	var d = doc.dataSets[i];
	d.remove();
}
```

I had to loop down since mutating an array while looping over it would only clear half of the elements.
