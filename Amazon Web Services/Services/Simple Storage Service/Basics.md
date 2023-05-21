---
aliases: [S3]
---

![[Pasted image 20230319220853.png]]
# Objects
![[Pasted image 20230319221246.png]]
- Can think of them as files
- **Private by default**
	- Only account root user has default access to this
## Components
1. key - similar to a filename. Identifies the object in a bucket
2. value - data or contents of the object
	 - Can store up to **zero bytes to 5TB per object**
3. Version ID
4. Metadata
5. Access Control
6. Subresources

# Bucket
![[Pasted image 20230319222506.png]]
- Bucket name  must be globally unique. Once a name exists, another bucket with the same name cannot be created even by other [[AWS Account|AWS accounts]] or in any AWS region.
- Can store unlimited objects
- Flat structure - All objects are stored at the same level unlike an actual file system where there is a concept of files and folders
- Prefixes resemble folders in a filesystem. For example we have a key `/old/Koala1.jpg` . The prefix here is `/old/` .
- 3  - 63 characters, all lower case, no underscores
- start with a lowercase letter or a number
- Can't be IP formatted e.g. 1.1.1.1
- Limit per [[AWS Account]] - **100 soft limit**, **1000 hard limit** that can be reached by submitting service limit increases
- **Private by default**

# Summary
![[Pasted image 20230319222840.png]]

# Patterns and Anti-Patterns
![[Pasted image 20230521040252.png]]