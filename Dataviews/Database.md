# Notes
```dataview
TABLE file.aliases as "Aliases", tags
 FROM #database AND #notes
 SORT tags ASC
```

```dataview
TABLE file.aliases as "Aliases", tags
 FROM #database AND #reference-notes
 SORT tags ASC
```