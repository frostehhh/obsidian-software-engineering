# Notes
```dataview
TABLE file.aliases as "Aliases", filter(tags, (tag) => tag != "notes" AND tag != "database") as Tags
 FROM #database AND #notes
 SORT tags ASC
```

# References Notes
```dataview
TABLE file.aliases as "Aliases", filter(tags, (tag) => tag != "reference-notes" AND tag != "database") as Tags
 FROM #database AND #reference-notes
 SORT tags ASC
```