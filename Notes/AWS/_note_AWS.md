Amazon Web Services

```dataview
TABLE filter(tags, (tag) => tag != "notes") as Tags
 FROM #aws
 SORT tags ASC
```