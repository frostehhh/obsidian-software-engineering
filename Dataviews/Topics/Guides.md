
# All
```dataview
TABLE filter(tags, (tag) => tag != "guide") as Tags
 FROM #notes AND #guide
 SORT tags ASC
```
