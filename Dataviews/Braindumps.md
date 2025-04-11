
# All
```dataview
TABLE file.tags as "Tags", file.ctime as "Created Datetime"
 FROM "Braindump"
 SORT file.ctime DESC
```

# Braindumps for Review

```dataview
TABLE file.tags as "Tags", file.ctime as "Created Datetime"
 FROM "Braindump"
WHERE for-review = "true"
 SORT file.ctime DESC
```