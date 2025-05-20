---
tags:
- notes
- aws/s3
aliases: S3
related-reference-note:: 
- "[[Reference Notes/Adrian Cantrill/Amazon Web Services/Services/Simple Storage Service/Basics|Basics]]"
---

- AWS cloud-based blob storage
# Multipart Uploads
- Split uploads into chunks/parts
	- Easily resumable on fail
- Best practice to consider multipart uploads when file size >=100mb
- Part size 5mb to 5gb
- Max size 5TB
- Part count 1 to 10,000

# References
https://aws.amazon.com/pm/serv-s3/?trk=55ffcfa3-95d3-4418-9a79-62a64040b867&sc_channel=ps&ef_id=Cj0KCQjw0LDBBhCnARIsAMpYlAoo7Q1FxxQmsZy7Y33XSug85khjL5_gKbgDctIARldH0Tn_J398VKAaAurVEALw_wcB:G:s&s_kwcid=AL!4422!3!536452732958!e!!g!!aws%20s3!11543056249!112002966709&gad_campaignid=11543056249&gbraid=0AAAAADjHtp-TFUGtqezvivrpYqt2tmt66&gclid=Cj0KCQjw0LDBBhCnARIsAMpYlAoo7Q1FxxQmsZy7Y33XSug85khjL5_gKbgDctIARldH0Tn_J398VKAaAurVEALw_wcB
https://docs.aws.amazon.com/AmazonS3/latest/userguide/qfacts.html