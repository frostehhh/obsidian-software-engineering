---
tags:
  - reference-notes
  - cryptography
  - system-design
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/consistent-hashing
"Friend:":
  - "[[Notes/Hashing|Hashing]]"
Draft: false
---

- Hashing a value always results to the same result

# Methods
## Modulo
`hash(value) % n = 0...n-1`

- Simple
- Problematic when the modulo changes; Will need to check each and every data record to process them since their hash could've changed after a modulo change

## Hash Ring
- Ring concept for acquiring hash result
- Hash space is 2\^32
- Improvement over modulo
- Example
```
For simplicity, hash space is 0-100
DB1 position 0
DB2 position 25
DB3 position 50
DB4 position 75

If we remove DB2, all values stores in DB2 will be moved to DB3

If we add a new DB5 at position 90, move records with hash result 75 to 90 to DB5
```

- Issue with this, redistribution of data on removal and addition of nodes results to imbalance of data

### Hash Ring with Virtual nodes
- Uses virtual nodes on top of the hash ring concept
- Example
```
Following the example previously,
DB1-vn1 0
DB2-vn1 6
DB3-vn1 12
DB4-vn1 18
...
```

# Consistent Hashing in System Design
- More frequently, just need to mention that we need to use consistent hashing w/o explanation how it works
- Otherwise, particularly in deep infrastructure system design interviews, need to articulate differences