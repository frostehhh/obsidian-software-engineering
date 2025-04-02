
# All
```dataview
TABLE filter(tags, (tag) => tag != "notes") as Tags
 FROM #backend AND #notes
 SORT tags ASC
```

# Communication
```dataview
TABLE file.aliases as "Aliases", filter(tags, (tag) => tag != "notes") as Tags
 FROM #backend/communication   AND #notes
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
```dataview
TABLE file.aliases as "Aliases", filter(tags, (tag) => tag != "notes") as Tags
 FROM #backend/communication/protocols AND #notes
 SORT tags ASC
```