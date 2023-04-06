```
echo "find all the doggos, distract them with the yumz" > battleplans.txt aws kms encrypt \ --key-id alias/catrobot \ --plaintext fileb://battleplans.txt \ --output text \ --query CiphertextBlob \ | base64 --decode > not_battleplans.enc aws kms decrypt \ --ciphertext-blob fileb://not_battleplans.enc \ --output text \ --query Plaintext | base64 --decode > decryptedplans.txt
```

--query CiphertextBlob - select certain Ciphertext field
output is text that is a binary encrypted file

# Related Course Demo
https://learn.cantrill.io/courses/1820301/lectures/41301480
