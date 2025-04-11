# All
```dataview
TABLE filter(tags, (tag) => tag != "flashcards") as Tags
 FROM "Anki"
```
```dataview
TABLE filter(tags, (tag) => tag != "flashcards") as Tags
 FROM "Anki"
WHERE Draft = true
```