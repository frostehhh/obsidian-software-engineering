
# All
```dataview
TABLE filter(tags, (tag) => tag != "notes") as Tags
 FROM #backend AND #notes
 SORT tags ASC
```

# Communication
```dataview
TABLE file.aliases as "Aliases", filter(tags, (tag) => tag != "notes") as Tags
 FROM #backend AND #communication   AND #notes
 SORT tags ASC
```


# Non-Communication
```dataview
TABLE file.aliases as "Aliases", filter(tags, (tag) => tag != "notes") as Tags
 FROM #backend AND #notes
WHERE contains(tags, "backend/communication") = false
 SORT tags ASC
```

# Protocols
## All
```dataview
TABLE file.aliases as "Aliases", filter(tags, (tag) => tag != "notes") as Tags
 FROM #backend AND #communication/protocols AND #notes
 SORT tags ASC
```

## HTTP
