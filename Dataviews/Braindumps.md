
```dataview
TABLE file.tags as "Tags", file.ctime as "Created Datetime"
 FROM "Braindump"
 SORT file.ctime DESC
```