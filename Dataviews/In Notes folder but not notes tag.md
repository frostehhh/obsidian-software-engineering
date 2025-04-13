```dataview
TABLE tags
FROM "Notes"
WHERE contains(tags, "notes") = false
```