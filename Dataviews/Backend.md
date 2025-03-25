
# All
```dataview
TABLE tags
 FROM #backend AND #notes
 SORT tags ASC
```

# Communication
```dataview
TABLE file.aliases as "Aliases", tags
 FROM #backend/communication   AND #notes
 SORT tags ASC
```

# Database
```dataview
TABLE file.aliases as "Aliases", tags
 FROM #database AND #notes
 SORT tags ASC
```