```dataview
TABLE file.aliases as "Aliases", tags
 FROM #system-design
 SORT tags ASC
WHERE contains(tags, "excalidraw") = false
```