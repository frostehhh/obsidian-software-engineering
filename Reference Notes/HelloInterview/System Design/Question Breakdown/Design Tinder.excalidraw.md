---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'

# Excalidraw Data

## Text Elements
Design a Dating App Like Tinder ^o5ipj4rW

Tinder is a mobile dating app that helps people connect by allowing users to swipe right to like or left
to pass on profiles. It uses location data and user-specified filters to suggest potential matches nearby. ^qJaaQeFB

Example ^iAPMCjGE

Functional Requirements:
- User can create tweets
- User can view tweets
- User can delete tweets
- ...

System Scale:
100M DAU, 500M tweets/day

Non-Functional Requirements:
- Availability > consistency
- Low latency feed gen
- ... ^S2aJ6hQh

Requirements ^4LiRDUki

Functional Requirements ^4k4JpHhQ

1. Users can create a profile with preferences (e.g. age range, interests) and specify a maximum distance.
2. Users can view a stack of potential matches in line with their preferences and within max distance of
their current location.
3. Users can swipe right / left on profiles one-by-one, to express 'yes' or 'no' on other users.
4. Users get a match notification if they mutually swipe on each other. ^xtjCZg5f

System Scale ^k8eDdlvK

- 20M daily active users ^rVCxoM2x

Non-Functional Requirements ^gxYH84kE

- eventually consistent viewing of profiles and retrieval of stack
- low latency retrieval of stack and profile data <300ms
- strongly consistent swipes
-  ^AumsOLqd

Example ^1wGNzo0o

Core Entities
- User
- Tweet
- Follow
         ^1dkgXBFq

Core Entities ^vltm07H5

- Stack - list of potential matches
- User
- Swipe
- Match ^lVQPXaeo

Example ^76nIDPr5

GET /feed -> Tweet[]

POST /tweet -> Tweet
body: {
    content: string
}

POST /follow -> void
{
    userId: string
} ^Xhzy7nqK

API Routes ^e0PJ612a

// get stack of potential matches based on the current user
GET /stack?lat=x&long=x&age_pref=x&gender_pref - User[] - 200
header: JWT - identifies user

POST /swipes - 201
body: {
    action: yes | no
    userId
}

GET /users/{id} - 200 ^2CFoR56p

POST /users - 200
{
  user - updates
} ^NdQZ487V

High-Level Design ^9E4aB6Qe

Simple Example ^ePRm2VNb

Client ^zl5b77Bw

Server ^RYgYDAsX

DB ^csnXMEiA

Client ^vzgZKCg1

Profile Service ^BeHPfxaq

PostgreSQ
L ^bcgn5W1t

User
- id
- name
- description
- gender - male or female
- location(lat, long)
- pref_min_age
- pref_max_age
- max_location_radius ^EPOMtH1I

POST /users ^AJ0PbggC

API 
Gateway/Load 
balancer ^TVMkZqW1

Stack Service ^H96WMEVb

GET /stack ^dq8x5Zxn

ElasticSearch ^8XUCoiyL

Index
User profile as listed above.
Filter out if current user has swiped before ^JATgm5t1

cdc ^g3qTTYf9

Swipe
- userId1
- userId2
- action - yes or no OR right or left or null
PK on userId1 and userId2
Add index on userId2 ^ajpA68av

20 million daily active users
swipes per day? 100

2 billion swipes per day
23000 swipes per second ^JkRAnzCe

Swipe - 33 - 3gb ^gqvtO460

User - 300 bytes -> 300gb ^RcOna4Uk

Cassandra ^ZBSfZa3S

Swipe ^8YA81gLi

partitionKey -> userId1:userId2
Should be sorted prior to storage
action - yes or no ^JNmFAsUB

Swipe Service ^DHAqNIce

POST /swipes ^WaPc30W9

Notification(AWS SNS) ^bzobBady

{
  userId1: a,
  userId2: b,
  user1_swipe: left,
  user2_swipe: right
} ^d2W8Qisd

Redis - keep 
very recent 
swipes - TTL
15 seconds ^PGRgBLaT

Local 
Storage - 
Stack -> 
100 to 150
entries ^B3qr0Ckd

Redis - stack per 
user LRU ^wU6WtXnl

cron daily ^ZcjGZhOb

cdc ^lz0D5YTA

CRON - daily - 
check for invalid 
swipes. Invalid if 
swipe no longer 
matches user 
preferences ^K1dSjRWq

## Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.15.0",
	"elements": [
		{
			"type": "text",
			"version": 2,
			"versionNonce": 607779752,
			"isDeleted": false,
			"id": "o5ipj4rW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0,
			"y": 0,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 717.9931640625,
			"height": 62.5,
			"seed": 314225209.61956125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 50,
			"fontFamily": 1,
			"text": "Design a Dating App Like Tinder",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Design a Dating App Like Tinder",
			"lineHeight": 1.25,
			"baseline": 43,
			"autoResize": true,
			"index": "a0",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 1362293464,
			"isDeleted": false,
			"id": "qJaaQeFB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0,
			"y": 100,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1356.8701171875,
			"height": 75,
			"seed": 340004461.2851973,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 30,
			"fontFamily": 1,
			"text": "Tinder is a mobile dating app that helps people connect by allowing users to swipe right to like or left\nto pass on profiles. It uses location data and user-specified filters to suggest potential matches nearby.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Tinder is a mobile dating app that helps people connect by allowing users to swipe right to like or left\nto pass on profiles. It uses location data and user-specified filters to suggest potential matches nearby.",
			"lineHeight": 1.25,
			"baseline": 64,
			"autoResize": true,
			"index": "a1",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 2,
			"versionNonce": 1171015336,
			"isDeleted": false,
			"id": "hi-work-area-requirements",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0,
			"y": 300,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1250,
			"height": 700,
			"seed": 760327304.7402151,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"index": "a2"
		},
		{
			"type": "arrow",
			"version": 2,
			"versionNonce": 16701400,
			"isDeleted": false,
			"id": "hi-cmb3pvcze3gpf08ad3xpxb9y1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -210,
			"y": 370,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 171.5,
			"height": 33,
			"seed": 260346323.218583,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"startBinding": null,
			"endBinding": {
				"elementId": "hi-work-area-requirements",
				"focus": 0,
				"gap": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					72.5,
					-33
				],
				[
					171.5,
					-13.75
				]
			],
			"index": "a3"
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 886911400,
			"isDeleted": false,
			"id": "iAPMCjGE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -265,
			"y": 381,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 77.8125,
			"height": 25,
			"seed": 581940321.0833856,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Example",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Example",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "a4",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 2013666520,
			"isDeleted": false,
			"id": "S2aJ6hQh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -265,
			"y": 415,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 216.9921875,
			"height": 260,
			"seed": 67358448.72974294,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Functional Requirements:\n- User can create tweets\n- User can view tweets\n- User can delete tweets\n- ...\n\nSystem Scale:\n100M DAU, 500M tweets/day\n\nNon-Functional Requirements:\n- Availability > consistency\n- Low latency feed gen\n- ...",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Functional Requirements:\n- User can create tweets\n- User can view tweets\n- User can delete tweets\n- ...\n\nSystem Scale:\n100M DAU, 500M tweets/day\n\nNon-Functional Requirements:\n- Availability > consistency\n- Low latency feed gen\n- ...",
			"lineHeight": 1.25,
			"baseline": 254,
			"autoResize": true,
			"index": "a5",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 144227496,
			"isDeleted": false,
			"id": "4LiRDUki",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 50,
			"y": 340,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 186.7529296875,
			"height": 37.5,
			"seed": 31942037.424730785,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 30,
			"fontFamily": 1,
			"text": "Requirements",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Requirements",
			"lineHeight": 1.25,
			"baseline": 26,
			"autoResize": true,
			"index": "a6",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 2010956248,
			"isDeleted": false,
			"id": "4k4JpHhQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 50,
			"y": 400,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 222.333984375,
			"height": 25,
			"seed": 418184287.3701953,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Functional Requirements",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Functional Requirements",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "a7",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 4,
			"versionNonce": 259081944,
			"isDeleted": false,
			"id": "xtjCZg5f",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 50,
			"y": 440,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 938.22265625,
			"height": 125,
			"seed": 168509721.7709388,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740795184,
			"link": null,
			"locked": true,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "1. Users can create a profile with preferences (e.g. age range, interests) and specify a maximum distance.\n2. Users can view a stack of potential matches in line with their preferences and within max distance of\ntheir current location.\n3. Users can swipe right / left on profiles one-by-one, to express 'yes' or 'no' on other users.\n4. Users get a match notification if they mutually swipe on each other.",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "1. Users can create a profile with preferences (e.g. age range, interests) and specify a maximum distance.\n2. Users can view a stack of potential matches in line with their preferences and within max distance of\ntheir current location.\n3. Users can swipe right / left on profiles one-by-one, to express 'yes' or 'no' on other users.\n4. Users get a match notification if they mutually swipe on each other.",
			"lineHeight": 1.25,
			"baseline": 117,
			"autoResize": true,
			"index": "a8",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 1872152280,
			"isDeleted": false,
			"id": "k8eDdlvK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 50,
			"y": 600,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 122.265625,
			"height": 25,
			"seed": 909027155.5995868,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "System Scale",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "System Scale",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "a9",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 255832744,
			"isDeleted": false,
			"id": "rVCxoM2x",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 50,
			"y": 630,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 210.078125,
			"height": 25,
			"seed": 950873885.5326557,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "- 20M daily active users",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- 20M daily active users",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "aA",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 1271409624,
			"isDeleted": false,
			"id": "gxYH84kE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 50,
			"y": 710,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 265.68359375,
			"height": 25,
			"seed": 803198314.5731518,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Non-Functional Requirements",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Non-Functional Requirements",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "aB",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 218,
			"versionNonce": 1426267560,
			"isDeleted": false,
			"id": "AumsOLqd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 48.33271858145088,
			"y": 745.6933800849232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 552.490234375,
			"height": 100,
			"seed": 201010611,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "- eventually consistent viewing of profiles and retrieval of stack\n- low latency retrieval of stack and profile data <300ms\n- strongly consistent swipes\n- ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- eventually consistent viewing of profiles and retrieval of stack\n- low latency retrieval of stack and profile data <300ms\n- strongly consistent swipes\n- ",
			"lineHeight": 1.25,
			"baseline": 92,
			"autoResize": true,
			"index": "aC",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 2,
			"versionNonce": 1183117528,
			"isDeleted": false,
			"id": "hi-work-area-core-entities",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0,
			"y": 1050,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1250,
			"height": 400,
			"seed": 57360716.533958025,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"index": "aD"
		},
		{
			"type": "arrow",
			"version": 2,
			"versionNonce": 86059176,
			"isDeleted": false,
			"id": "hi-cmb3r3yy5000c356wiql63n9e",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -210,
			"y": 1090,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 171.5,
			"height": 33,
			"seed": 2011310.5306670542,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"startBinding": null,
			"endBinding": {
				"elementId": "hi-work-area-core-entities",
				"focus": 0,
				"gap": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					72.5,
					-33
				],
				[
					171.5,
					-13.75
				]
			],
			"index": "aE"
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 929109464,
			"isDeleted": false,
			"id": "1wGNzo0o",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -265,
			"y": 1101,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 77.8125,
			"height": 25,
			"seed": 67717903.52504803,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Example",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Example",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "aF",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 994431912,
			"isDeleted": false,
			"id": "1dkgXBFq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -265,
			"y": 1135,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 91.59375,
			"height": 100,
			"seed": 820589242.0547596,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Core Entities\n- User\n- Tweet\n- Follow\n        ",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Core Entities\n- User\n- Tweet\n- Follow\n        ",
			"lineHeight": 1.25,
			"baseline": 94,
			"autoResize": true,
			"index": "aG",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 1668324056,
			"isDeleted": false,
			"id": "vltm07H5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 50,
			"y": 1100,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 171.73828125,
			"height": 37.5,
			"seed": 345376044.3062841,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 30,
			"fontFamily": 1,
			"text": "Core Entities",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Core Entities",
			"lineHeight": 1.25,
			"baseline": 26,
			"autoResize": true,
			"index": "aH",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 87,
			"versionNonce": 1033707176,
			"isDeleted": false,
			"id": "lVQPXaeo",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 54.31446751036407,
			"y": 1167.0895189244861,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 289.00390625,
			"height": 100,
			"seed": 1183302963,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "- Stack - list of potential matches\n- User\n- Swipe\n- Match",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- Stack - list of potential matches\n- User\n- Swipe\n- Match",
			"lineHeight": 1.25,
			"baseline": 92,
			"autoResize": true,
			"index": "aI",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 2,
			"versionNonce": 1296531416,
			"isDeleted": false,
			"id": "hi-work-area-api",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0,
			"y": 1500,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 1250,
			"height": 900,
			"seed": 43577182.998760015,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"index": "aJ"
		},
		{
			"type": "arrow",
			"version": 2,
			"versionNonce": 752028072,
			"isDeleted": false,
			"id": "hi-cmb3r5wqr0012356wn94f5m1q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -210,
			"y": 1590,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 171.5,
			"height": 33,
			"seed": 624538539.8382959,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"startBinding": null,
			"endBinding": {
				"elementId": "hi-work-area-api",
				"focus": 0,
				"gap": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					72.5,
					-33
				],
				[
					171.5,
					-13.75
				]
			],
			"index": "aK"
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 83477720,
			"isDeleted": false,
			"id": "76nIDPr5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -265,
			"y": 1601,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 77.8125,
			"height": 25,
			"seed": 223773716.3997281,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Example",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Example",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "aL",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 873698472,
			"isDeleted": false,
			"id": "Xhzy7nqK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -265,
			"y": 1635,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 156.9453125,
			"height": 220,
			"seed": 7714546.467699313,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "GET /feed -> Tweet[]\n\nPOST /tweet -> Tweet\nbody: {\n    content: string\n}\n\nPOST /follow -> void\n{\n    userId: string\n}",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "GET /feed -> Tweet[]\n\nPOST /tweet -> Tweet\nbody: {\n    content: string\n}\n\nPOST /follow -> void\n{\n    userId: string\n}",
			"lineHeight": 1.25,
			"baseline": 214,
			"autoResize": true,
			"index": "aM",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 2015062488,
			"isDeleted": false,
			"id": "e0PJ612a",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 50,
			"y": 1550,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 151.7431640625,
			"height": 37.5,
			"seed": 503137866.6242396,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 30,
			"fontFamily": 1,
			"text": "API Routes",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "API Routes",
			"lineHeight": 1.25,
			"baseline": 26,
			"autoResize": true,
			"index": "aN",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 368,
			"versionNonce": 957005736,
			"isDeleted": false,
			"id": "2CFoR56p",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 62.531371704502135,
			"y": 1616.3705293811765,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 583.095703125,
			"height": 275,
			"seed": 1379100157,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "// get stack of potential matches based on the current user\nGET /stack?lat=x&long=x&age_pref=x&gender_pref - User[] - 200\nheader: JWT - identifies user\n\nPOST /swipes - 201\nbody: {\n    action: yes | no\n    userId\n}\n\nGET /users/{id} - 200",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "// get stack of potential matches based on the current user\nGET /stack?lat=x&long=x&age_pref=x&gender_pref - User[] - 200\nheader: JWT - identifies user\n\nPOST /swipes - 201\nbody: {\n    action: yes | no\n    userId\n}\n\nGET /users/{id} - 200",
			"lineHeight": 1.25,
			"baseline": 267,
			"autoResize": true,
			"index": "aO",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 88,
			"versionNonce": 1103130328,
			"isDeleted": false,
			"id": "NdQZ487V",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 62.53137170450191,
			"y": 1931.3750730188829,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 165.615234375,
			"height": 100,
			"seed": 273713043,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "POST /users - 200\n{\n  user - updates\n}",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "POST /users - 200\n{\n  user - updates\n}",
			"lineHeight": 1.25,
			"baseline": 92,
			"autoResize": true,
			"index": "aP",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 2,
			"versionNonce": 199527080,
			"isDeleted": false,
			"id": "hi-work-area-high-level-design",
			"fillStyle": "hachure",
			"strokeWidth": 10,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1300,
			"y": 300,
			"strokeColor": "#299a8d",
			"backgroundColor": "transparent",
			"width": 3500,
			"height": 2100,
			"seed": 290081749.0715787,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"index": "aQ"
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 2055001048,
			"isDeleted": false,
			"id": "9E4aB6Qe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1350,
			"y": 350,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 245.126953125,
			"height": 37.5,
			"seed": 253481275.33496156,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": true,
			"fontSize": 30,
			"fontFamily": 1,
			"text": "High-Level Design",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "High-Level Design",
			"lineHeight": 1.25,
			"baseline": 26,
			"autoResize": true,
			"index": "aR",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 2,
			"versionNonce": 390919592,
			"isDeleted": false,
			"id": "hi-cmb3rd0sn001u356w97tbd0wo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5150,
			"y": 510,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 280,
			"height": 60,
			"seed": 409983206.1721511,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "hi-work-area-high-level-design",
				"focus": 0,
				"gap": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "triangle",
			"points": [
				[
					0,
					0
				],
				[
					-100,
					-60
				],
				[
					-280,
					-25
				]
			],
			"index": "aS"
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 140810456,
			"isDeleted": false,
			"id": "ePRm2VNb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5150,
			"y": 530,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 144.501953125,
			"height": 25,
			"seed": 862076984.629596,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Simple Example",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Simple Example",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "aT",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 2,
			"versionNonce": 275775656,
			"isDeleted": false,
			"id": "hi-cmb3rd0sn001x356wtpdpo1u8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5150,
			"y": 560,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 100,
			"height": 100,
			"seed": 10864337.727828577,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"index": "aU"
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 1863040472,
			"isDeleted": false,
			"id": "zl5b77Bw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5180,
			"y": 602,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 40.90625,
			"height": 20,
			"seed": 200698873.01835442,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Client",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Client",
			"lineHeight": 1.25,
			"baseline": 14,
			"autoResize": true,
			"index": "aV",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 2,
			"versionNonce": 653896616,
			"isDeleted": false,
			"id": "hi-cmb3rd0sn001z356we72wztsh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5260,
			"y": 610,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 50,
			"height": 0,
			"seed": 642392077.1129618,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "hi-cmb3rd0sn001x356wtpdpo1u8",
				"focus": 0,
				"gap": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					50,
					0
				]
			],
			"index": "aW"
		},
		{
			"type": "rectangle",
			"version": 2,
			"versionNonce": 528892632,
			"isDeleted": false,
			"id": "hi-cmb3rd0sn0020356weku8xcsn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5320,
			"y": 510,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 100,
			"height": 200,
			"seed": 126934507.84846982,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"index": "aX"
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 890631848,
			"isDeleted": false,
			"id": "RYgYDAsX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5340,
			"y": 602,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 47.125,
			"height": 20,
			"seed": 963519717.7631028,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Server",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Server",
			"lineHeight": 1.25,
			"baseline": 14,
			"autoResize": true,
			"index": "aY",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 2,
			"versionNonce": 1214785496,
			"isDeleted": false,
			"id": "hi-cmb3rd0sn0022356wp66vfy3o",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5430,
			"y": 610,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 50,
			"height": 0,
			"seed": 923655818.6525766,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "hi-cmb3rd0sn0020356weku8xcsn",
				"focus": 0,
				"gap": 0
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					50,
					0
				]
			],
			"index": "aZ"
		},
		{
			"type": "rectangle",
			"version": 2,
			"versionNonce": 1869668776,
			"isDeleted": false,
			"id": "hi-cmb3rd0sn0023356wvs7fkynz",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5490,
			"y": 560,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 100,
			"height": 100,
			"seed": 601837110.791378,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"index": "aa"
		},
		{
			"type": "text",
			"version": 2,
			"versionNonce": 633695448,
			"isDeleted": false,
			"id": "csnXMEiA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 5520,
			"y": 602,
			"strokeColor": "#B8B8B8",
			"backgroundColor": "transparent",
			"width": 22.2265625,
			"height": 20,
			"seed": 993308687.3549435,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "DB",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DB",
			"lineHeight": 1.25,
			"baseline": 14,
			"autoResize": true,
			"index": "ab",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 574,
			"versionNonce": 355888296,
			"isDeleted": false,
			"id": "8Jqv25E445zGyZfKEH9ky",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1586.5051553159283,
			"y": 967.6544874566807,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.2666910432174,
			"height": 118.2666910432174,
			"seed": 410097491,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "vzgZKCg1"
				},
				{
					"id": "vkLo8Z7jeu9pfbvLzTwi_",
					"type": "arrow"
				},
				{
					"id": "q3cFKw6jaWCNrAKdMnnHv",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "ac"
		},
		{
			"type": "text",
			"version": 490,
			"versionNonce": 1871271592,
			"isDeleted": false,
			"id": "vzgZKCg1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1618.5885283033572,
			"y": 1014.2878329782894,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 54.099945068359375,
			"height": 25,
			"seed": 994833395,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781052,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Client",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "8Jqv25E445zGyZfKEH9ky",
			"originalText": "Client",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "ad",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 513,
			"versionNonce": 538089384,
			"isDeleted": false,
			"id": "J95HtVYHp0z1TBRuiIPRW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2522.6007227633995,
			"y": 970.2282509738505,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 201.33491916627526,
			"height": 118.2666910432174,
			"seed": 114602451,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "BeHPfxaq"
				},
				{
					"id": "uPzG9x5Pn9KrmVPH64-bQ",
					"type": "arrow"
				},
				{
					"id": "sGoz3z15OuiT0-wTJyFru",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "ae"
		},
		{
			"type": "text",
			"version": 535,
			"versionNonce": 1989553576,
			"isDeleted": false,
			"id": "BeHPfxaq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2552.908258030131,
			"y": 1016.8615964954593,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 140.7198486328125,
			"height": 25,
			"seed": 61144947,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781104,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Profile Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "J95HtVYHp0z1TBRuiIPRW",
			"originalText": "Profile Service",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "af",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 335,
			"versionNonce": 1949393576,
			"isDeleted": false,
			"id": "X4oDtrSuZryJ_tCos31WC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2911.6960966361708,
			"y": 972.9415617271173,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 112.50696522417893,
			"height": 126.03238335648416,
			"seed": 1818232573,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "bcgn5W1t"
				},
				{
					"id": "sGoz3z15OuiT0-wTJyFru",
					"type": "arrow"
				},
				{
					"id": "AY5RzRGZDvEB52rfxJ6U5",
					"type": "arrow"
				},
				{
					"id": "c8jtJD7xUicnjt2L30LjF",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "ag"
		},
		{
			"type": "text",
			"version": 314,
			"versionNonce": 666674344,
			"isDeleted": false,
			"id": "bcgn5W1t",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2920.4405460451353,
			"y": 1012.7230244070145,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 95.01806640625,
			"height": 46.4694579966899,
			"seed": 578778013,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781108,
			"link": null,
			"locked": false,
			"fontSize": 18.587783198675957,
			"fontFamily": 1,
			"text": "PostgreSQ\nL",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "X4oDtrSuZryJ_tCos31WC",
			"originalText": "PostgreSQ\nL",
			"lineHeight": 1.25,
			"baseline": 39,
			"autoResize": true,
			"index": "ah",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 443,
			"versionNonce": 272551336,
			"isDeleted": false,
			"id": "EPOMtH1I",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3054.7557395438234,
			"y": 983.1770487283911,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 224.541015625,
			"height": 225,
			"seed": 260759357,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "User\n- id\n- name\n- description\n- gender - male or female\n- location(lat, long)\n- pref_min_age\n- pref_max_age\n- max_location_radius",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "User\n- id\n- name\n- description\n- gender - male or female\n- location(lat, long)\n- pref_min_age\n- pref_max_age\n- max_location_radius",
			"lineHeight": 1.25,
			"baseline": 217,
			"autoResize": true,
			"index": "ai",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 1176,
			"versionNonce": 47152296,
			"isDeleted": false,
			"id": "uPzG9x5Pn9KrmVPH64-bQ",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2178.51217730006,
			"y": 1017.3201151534698,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 325.4041290364462,
			"height": 1.8521053770803064,
			"seed": 81099347,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "AJ0PbggC"
				}
			],
			"updated": 1756740781120,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zHPOMu2nPSpyEusWt_FhV",
				"focus": -0.062424533633782225,
				"gap": 24.350452426475726
			},
			"endBinding": {
				"elementId": "J95HtVYHp0z1TBRuiIPRW",
				"focus": 0.24407640462651478,
				"gap": 18.68441642689345
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					325.4041290364462,
					-1.8521053770803064
				]
			],
			"customData": {
				"legacyTextWrap": true
			},
			"index": "aj"
		},
		{
			"type": "text",
			"version": 14,
			"versionNonce": 1062527912,
			"isDeleted": false,
			"id": "AJ0PbggC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2283.977913693283,
			"y": 1003.8940624649296,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 128.59988403320312,
			"height": 25,
			"seed": 1447453565,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781107,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "POST /users",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "uPzG9x5Pn9KrmVPH64-bQ",
			"originalText": "POST /users",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "ak",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 822,
			"versionNonce": 1964101544,
			"isDeleted": false,
			"id": "sGoz3z15OuiT0-wTJyFru",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2737.9147410308865,
			"y": 1018.5531472140981,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 168.33889739793085,
			"height": 1.8851296837085556,
			"seed": 789968851,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740781109,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "J95HtVYHp0z1TBRuiIPRW",
				"focus": -0.2006527392906668,
				"gap": 13.979099101211204
			},
			"endBinding": {
				"elementId": "X4oDtrSuZryJ_tCos31WC",
				"focus": 0.23298473444262965,
				"gap": 5.442458207353411
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					168.33889739793085,
					1.8851296837085556
				]
			],
			"index": "al"
		},
		{
			"type": "rectangle",
			"version": 740,
			"versionNonce": 1062568872,
			"isDeleted": false,
			"id": "zHPOMu2nPSpyEusWt_FhV",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1987.1453227426548,
			"y": 779.6957362780873,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 167.01640213092955,
			"height": 508.26404500746736,
			"seed": 805459453,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "TVMkZqW1"
				},
				{
					"id": "uPzG9x5Pn9KrmVPH64-bQ",
					"type": "arrow"
				},
				{
					"id": "vkLo8Z7jeu9pfbvLzTwi_",
					"type": "arrow"
				},
				{
					"id": "I_WMhvR0f1QSthb_iWhwC",
					"type": "arrow"
				},
				{
					"id": "C-7wILdBZq2WIRTcBIv7j",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "am"
		},
		{
			"type": "text",
			"version": 928,
			"versionNonce": 1592521128,
			"isDeleted": false,
			"id": "TVMkZqW1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1993.633565312026,
			"y": 996.327758781821,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 154.0399169921875,
			"height": 75,
			"seed": 1218481757,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781120,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "API \nGateway/Load \nbalancer",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "zHPOMu2nPSpyEusWt_FhV",
			"originalText": "API \nGateway/Load \nbalancer",
			"lineHeight": 1.25,
			"baseline": 67,
			"autoResize": true,
			"index": "an",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 514,
			"versionNonce": 403285928,
			"isDeleted": false,
			"id": "vkLo8Z7jeu9pfbvLzTwi_",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1725.140210079699,
			"y": 1029.3095709197228,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 242.52955323984634,
			"height": 5.525822309056139,
			"seed": 766950461,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740781121,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "8Jqv25E445zGyZfKEH9ky",
				"focus": 0.07164464361654059,
				"gap": 20.368363720553475
			},
			"endBinding": {
				"elementId": "zHPOMu2nPSpyEusWt_FhV",
				"focus": 0.04839346103204647,
				"gap": 19.47555942310953
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					242.52955323984634,
					-5.525822309056139
				]
			],
			"index": "ao"
		},
		{
			"type": "rectangle",
			"version": 644,
			"versionNonce": 442552280,
			"isDeleted": false,
			"id": "wleRC_l8vq9nwHlTuExE2",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2483.6857528899873,
			"y": 1273.4476736398442,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 201.33491916627526,
			"height": 118.2666910432174,
			"seed": 1233594867,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "H96WMEVb"
				},
				{
					"id": "I_WMhvR0f1QSthb_iWhwC",
					"type": "arrow"
				},
				{
					"id": "ggRZ1wiD8RXRM81ITHIiv",
					"type": "arrow"
				},
				{
					"id": "QYX8zbi08ZqJDbmFDq0wE",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "ap"
		},
		{
			"type": "text",
			"version": 675,
			"versionNonce": 1277282728,
			"isDeleted": false,
			"id": "H96WMEVb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2517.3032704565235,
			"y": 1320.0810191614528,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 134.09988403320312,
			"height": 25,
			"seed": 361984915,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781152,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Stack Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "wleRC_l8vq9nwHlTuExE2",
			"originalText": "Stack Service",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "aq",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 607,
			"versionNonce": 2072663208,
			"isDeleted": false,
			"id": "I_WMhvR0f1QSthb_iWhwC",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2171.199726215861,
			"y": 1074.994469780168,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 296.1543804892226,
			"height": 245.41344124678403,
			"seed": 1872863027,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "dq8x5Zxn"
				}
			],
			"updated": 1756740781172,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zHPOMu2nPSpyEusWt_FhV",
				"focus": -0.13036929850748383,
				"gap": 17.038001342276743
			},
			"endBinding": {
				"elementId": "wleRC_l8vq9nwHlTuExE2",
				"focus": -0.5947269966541787,
				"gap": 16.331646184903775
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					296.1543804892226,
					245.41344124678403
				]
			],
			"customData": {
				"legacyTextWrap": true
			},
			"index": "ar"
		},
		{
			"type": "text",
			"version": 21,
			"versionNonce": 565304744,
			"isDeleted": false,
			"id": "dq8x5Zxn",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2269.823791460472,
			"y": 1185.2011904035598,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 120.61993408203125,
			"height": 25,
			"seed": 1594392125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781139,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "GET /stack",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "I_WMhvR0f1QSthb_iWhwC",
			"originalText": "GET /stack",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "as",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 449,
			"versionNonce": 723565016,
			"isDeleted": false,
			"id": "i5TlssxH7JjmtnCuEYUU0",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2852.958391412287,
			"y": 1260.424152048813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 136.8817649784603,
			"height": 126.03238335648416,
			"seed": 609218899,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "8XUCoiyL"
				},
				{
					"id": "AY5RzRGZDvEB52rfxJ6U5",
					"type": "arrow"
				},
				{
					"id": "ggRZ1wiD8RXRM81ITHIiv",
					"type": "arrow"
				},
				{
					"id": "qWOPCd5F8M4x_hjAU_Byp",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "at"
		},
		{
			"type": "text",
			"version": 440,
			"versionNonce": 109494440,
			"isDeleted": false,
			"id": "8XUCoiyL",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2859.3328295045444,
			"y": 1311.8229792278828,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 124.13288879394531,
			"height": 23.23472899834495,
			"seed": 1586253555,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781182,
			"link": null,
			"locked": false,
			"fontSize": 18.587783198675957,
			"fontFamily": 1,
			"text": "ElasticSearch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "i5TlssxH7JjmtnCuEYUU0",
			"originalText": "ElasticSearch",
			"lineHeight": 1.25,
			"baseline": 16,
			"autoResize": true,
			"index": "au",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 272,
			"versionNonce": 127647448,
			"isDeleted": false,
			"id": "JATgm5t1",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3029.1372639419997,
			"y": 1299.0650880887263,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 373.505859375,
			"height": 75,
			"seed": 513811123,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Index\nUser profile as listed above.\nFilter out if current user has swiped before",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Index\nUser profile as listed above.\nFilter out if current user has swiped before",
			"lineHeight": 1.25,
			"baseline": 67,
			"autoResize": true,
			"index": "av",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 575,
			"versionNonce": 741895080,
			"isDeleted": false,
			"id": "AY5RzRGZDvEB52rfxJ6U5",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2954.4894479986,
			"y": 1111.4629138128428,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 31.233951186659397,
			"height": 133.3686923382179,
			"seed": 1743900595,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "g3qTTYf9"
				}
			],
			"updated": 1756740781193,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "X4oDtrSuZryJ_tCos31WC",
				"focus": -0.05843360317381246,
				"gap": 12.488968729241378
			},
			"endBinding": {
				"elementId": "i5TlssxH7JjmtnCuEYUU0",
				"focus": -0.1989614671207319,
				"gap": 15.592545897752416
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-31.233951186659397,
					133.3686923382179
				]
			],
			"customData": {
				"legacyTextWrap": true
			},
			"index": "aw"
		},
		{
			"type": "text",
			"version": 6,
			"versionNonce": 684721576,
			"isDeleted": false,
			"id": "g3qTTYf9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2923.5839168467314,
			"y": 1165.647259981952,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 31.459976196289062,
			"height": 25,
			"seed": 767529939,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781118,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "cdc",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "AY5RzRGZDvEB52rfxJ6U5",
			"originalText": "cdc",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "ax",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 698,
			"versionNonce": 612153000,
			"isDeleted": false,
			"id": "ggRZ1wiD8RXRM81ITHIiv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2711.102327406197,
			"y": 1323.782214766896,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 124.9850357761843,
			"height": 1.0276547746464075,
			"seed": 905269629,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740781193,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wleRC_l8vq9nwHlTuExE2",
				"focus": -0.12938873058288367,
				"gap": 26.08165534993509
			},
			"endBinding": {
				"elementId": "i5TlssxH7JjmtnCuEYUU0",
				"focus": 0.021819135594274956,
				"gap": 16.871028229905505
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					124.9850357761843,
					-1.0276547746464075
				]
			],
			"index": "ay"
		},
		{
			"type": "text",
			"version": 580,
			"versionNonce": 1806428376,
			"isDeleted": false,
			"id": "ajpA68av",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3379.443166487776,
			"y": 1015.6932080754433,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 361.25,
			"height": 150,
			"seed": 757180861,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Swipe\n- userId1\n- userId2\n- action - yes or no OR right or left or null\nPK on userId1 and userId2\nAdd index on userId2",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Swipe\n- userId1\n- userId2\n- action - yes or no OR right or left or null\nPK on userId1 and userId2\nAdd index on userId2",
			"lineHeight": 1.25,
			"baseline": 142,
			"autoResize": true,
			"index": "az",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 228,
			"versionNonce": 1678094504,
			"isDeleted": false,
			"id": "JkRAnzCe",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3496.054003486966,
			"y": 1217.5918916967044,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 243.4375,
			"height": 125,
			"seed": 868692147,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "20 million daily active users\nswipes per day? 100\n\n2 billion swipes per day\n23000 swipes per second",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "20 million daily active users\nswipes per day? 100\n\n2 billion swipes per day\n23000 swipes per second",
			"lineHeight": 1.25,
			"baseline": 117,
			"autoResize": true,
			"index": "b00",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 216600024,
			"isDeleted": false,
			"id": "gqvtO460",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3420.835337479317,
			"y": 931.1580060547053,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 145.634765625,
			"height": 25,
			"seed": 622856125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Swipe - 33 - 3gb",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Swipe - 33 - 3gb",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "b01",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 277,
			"versionNonce": 1549360040,
			"isDeleted": false,
			"id": "RcOna4Uk",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3050.120490967486,
			"y": 918.1711802214884,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 231.796875,
			"height": 25,
			"seed": 1930514003,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "User - 300 bytes -> 300gb",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "User - 300 bytes -> 300gb",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "b02",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 481,
			"versionNonce": 892965592,
			"isDeleted": false,
			"id": "6mVULzuWQ14Hm8ow8tatz",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2901.5382029643533,
			"y": 720.0500581747939,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 133.0166037660697,
			"height": 155.82061385323613,
			"seed": 1930100765,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"id": "DawE-vTV3FHYwAaEcKe8n",
					"type": "arrow"
				},
				{
					"id": "c8jtJD7xUicnjt2L30LjF",
					"type": "arrow"
				},
				{
					"id": "nWv-AT7YbatJx9ub3PBYU",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b03"
		},
		{
			"type": "text",
			"version": 262,
			"versionNonce": 50308776,
			"isDeleted": false,
			"id": "ZBSfZa3S",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2918.6294982315926,
			"y": 672.1913365437597,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 96.71875,
			"height": 25,
			"seed": 1295538227,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Cassandra",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Cassandra",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "b04",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 129,
			"versionNonce": 1798404056,
			"isDeleted": false,
			"id": "tcbbhr47y29v_qDdGQ0YW",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2918.281200566804,
			"y": 747.7924491590464,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 98.33343505859375,
			"height": 96.66664123535156,
			"seed": 590075347,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "8YA81gLi"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b05"
		},
		{
			"type": "text",
			"version": 59,
			"versionNonce": 439886504,
			"isDeleted": false,
			"id": "8YA81gLi",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2942.6879464774483,
			"y": 783.6257697767222,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 49.51994323730469,
			"height": 25,
			"seed": 52844275,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781210,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Swipe",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "tcbbhr47y29v_qDdGQ0YW",
			"originalText": "Swipe",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "b06",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 151,
			"versionNonce": 1122286808,
			"isDeleted": false,
			"id": "JNmFAsUB",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3068.8764822585817,
			"y": 761.5544011505364,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 291.2890625,
			"height": 75,
			"seed": 864515709,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "partitionKey -> userId1:userId2\nShould be sorted prior to storage\naction - yes or no",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "partitionKey -> userId1:userId2\nShould be sorted prior to storage\naction - yes or no",
			"lineHeight": 1.25,
			"baseline": 67,
			"autoResize": true,
			"index": "b07",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 581,
			"versionNonce": 1484004520,
			"isDeleted": false,
			"id": "LgmwseVQvILjUYlnCBndN",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2509.637594104013,
			"y": 766.2306085028114,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 201.33491916627526,
			"height": 118.2666910432174,
			"seed": 530607987,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "DHAqNIce"
				},
				{
					"id": "C-7wILdBZq2WIRTcBIv7j",
					"type": "arrow"
				},
				{
					"id": "DawE-vTV3FHYwAaEcKe8n",
					"type": "arrow"
				},
				{
					"id": "q3cFKw6jaWCNrAKdMnnHv",
					"type": "arrow"
				},
				{
					"id": "CHYy9Yhqe3mpI-cdnAxZM",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b08"
		},
		{
			"type": "text",
			"version": 613,
			"versionNonce": 549296296,
			"isDeleted": false,
			"id": "DHAqNIce",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2546.7851180792404,
			"y": 812.8639540244201,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 127.03987121582031,
			"height": 25,
			"seed": 862456083,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781210,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Swipe Service",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "LgmwseVQvILjUYlnCBndN",
			"originalText": "Swipe Service",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "b09",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 51,
			"versionNonce": 164905896,
			"isDeleted": false,
			"id": "C-7wILdBZq2WIRTcBIv7j",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2168.8764822585795,
			"y": 975.8401590327903,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 323.8095528738836,
			"height": 140,
			"seed": 2098428275,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "WaPc30W9"
				}
			],
			"updated": 1756740781222,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "zHPOMu2nPSpyEusWt_FhV",
				"focus": -0.05347566533418147,
				"gap": 14.714757384995096
			},
			"endBinding": {
				"elementId": "LgmwseVQvILjUYlnCBndN",
				"focus": 0.3933159446345353,
				"gap": 16.951558971549503
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					323.8095528738836,
					-140
				]
			],
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b0A"
		},
		{
			"type": "text",
			"version": 17,
			"versionNonce": 994349992,
			"isDeleted": false,
			"id": "WaPc30W9",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2267.4316493205215,
			"y": 893.3401590327903,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 135.05987548828125,
			"height": 25,
			"seed": 588759315,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781152,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "POST /swipes",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "C-7wILdBZq2WIRTcBIv7j",
			"originalText": "POST /swipes",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "b0B",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 41,
			"versionNonce": 282955432,
			"isDeleted": false,
			"id": "DawE-vTV3FHYwAaEcKe8n",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2731.1619640294116,
			"y": 824.1972045243273,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 160.00000000000045,
			"height": 26.66665213448664,
			"seed": 145642067,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740781230,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "LgmwseVQvILjUYlnCBndN",
				"focus": 0.2499768984967267,
				"gap": 20.189450759123474
			},
			"endBinding": {
				"elementId": "6mVULzuWQ14Hm8ow8tatz",
				"focus": 0.14881614928886033,
				"gap": 10.376238934941057
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					160.00000000000045,
					-26.66665213448664
				]
			],
			"index": "b0C"
		},
		{
			"type": "arrow",
			"version": 330,
			"versionNonce": 512063912,
			"isDeleted": false,
			"id": "q3cFKw6jaWCNrAKdMnnHv",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2585.828729514903,
			"y": 746.7210750832928,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 928,
			"height": 281.3333740234376,
			"seed": 1232296893,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "bzobBady"
				}
			],
			"updated": 1756740781248,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "LgmwseVQvILjUYlnCBndN",
				"focus": 0.7955591484344375,
				"gap": 19.50953341951856
			},
			"endBinding": {
				"elementId": "8Jqv25E445zGyZfKEH9ky",
				"focus": -0.5119833336719047,
				"gap": 12.933412373387796
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-242.6666259765625,
					-73.3333740234375
				],
				[
					-526.6666259765625,
					-72
				],
				[
					-760,
					42.6666259765625
				],
				[
					-928,
					208.0000000000001
				]
			],
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b0D"
		},
		{
			"type": "text",
			"version": 32,
			"versionNonce": 583137192,
			"isDeleted": false,
			"id": "bzobBady",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1957.2871035383405,
			"y": 662.2210750832928,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 215.6798095703125,
			"height": 25,
			"seed": 2118849789,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781104,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Notification(AWS SNS)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "q3cFKw6jaWCNrAKdMnnHv",
			"originalText": "Notification(AWS SNS)",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "b0E",
			"rawText": ""
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 1561563352,
			"isDeleted": false,
			"id": "d2W8Qisd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3588.4950503156842,
			"y": 654.7211056008709,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 173.41796875,
			"height": 150,
			"seed": 875247069,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "{\n  userId1: a,\n  userId2: b,\n  user1_swipe: left,\n  user2_swipe: right\n}",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "{\n  userId1: a,\n  userId2: b,\n  user1_swipe: left,\n  user2_swipe: right\n}",
			"lineHeight": 1.25,
			"baseline": 142,
			"autoResize": true,
			"index": "b0F",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 260,
			"versionNonce": 1548519592,
			"isDeleted": false,
			"id": "GerBIVCKR6C3yrZwjoJMD",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2667.8522120646608,
			"y": 502.24504700421426,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 150.71432931082566,
			"height": 135,
			"seed": 890817437,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "PGRgBLaT"
				},
				{
					"id": "CHYy9Yhqe3mpI-cdnAxZM",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b0G"
		},
		{
			"type": "text",
			"version": 294,
			"versionNonce": 1131215528,
			"isDeleted": false,
			"id": "PGRgBLaT",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2677.4894365345267,
			"y": 519.7450470042143,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 131.43988037109375,
			"height": 100,
			"seed": 2056736765,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781257,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Redis - keep \nvery recent \nswipes - TTL\n15 seconds",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "GerBIVCKR6C3yrZwjoJMD",
			"originalText": "Redis - keep \nvery recent \nswipes - TTL\n15 seconds",
			"lineHeight": 1.25,
			"baseline": 92,
			"autoResize": true,
			"index": "b0H",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 67,
			"versionNonce": 608658856,
			"isDeleted": false,
			"id": "CHYy9Yhqe3mpI-cdnAxZM",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2699.9200339040676,
			"y": 746.4363781319926,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.5171408531196,
			"height": 90.14368119927656,
			"seed": 891844957,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740781266,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "LgmwseVQvILjUYlnCBndN",
				"focus": 0.5224901776921516,
				"gap": 22.31884941886767
			},
			"endBinding": {
				"elementId": "GerBIVCKR6C3yrZwjoJMD",
				"focus": -0.16829027942588462,
				"gap": 19.04764992850164
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					30.5171408531196,
					-90.14368119927656
				]
			],
			"index": "b0I"
		},
		{
			"type": "rectangle",
			"version": 215,
			"versionNonce": 1591163608,
			"isDeleted": false,
			"id": "Is-BgAuV6fbweTwl2B-ue",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1567.0116137312116,
			"y": 958.6146831765545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 157.1428571428571,
			"height": 376.19044712611617,
			"seed": 1156876627,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"index": "b0J"
		},
		{
			"type": "rectangle",
			"version": 664,
			"versionNonce": 158367400,
			"isDeleted": false,
			"id": "l2BMiijfqZdLjtlu9FRyA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1583.1162181258976,
			"y": 1108.0526354367535,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.2666910432174,
			"height": 135,
			"seed": 2123861661,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "B3qr0Ckd"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b0K"
		},
		{
			"type": "text",
			"version": 647,
			"versionNonce": 739777448,
			"isDeleted": false,
			"id": "B3qr0Ckd",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 1588.8195938599088,
			"y": 1113.0526354367535,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 106.85993957519531,
			"height": 125,
			"seed": 1296413437,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Local \nStorage - \nStack -> \n100 to 150\nentries",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "l2BMiijfqZdLjtlu9FRyA",
			"originalText": "Local \nStorage - \nStack -> \n100 to 150\nentries",
			"lineHeight": 1.25,
			"baseline": 117,
			"autoResize": true,
			"index": "b0L",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 814,
			"versionNonce": 1731881384,
			"isDeleted": false,
			"id": "jra1MMAikiPC-gJj9GZCj",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2594.058617154959,
			"y": 1523.4334395894703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 201.33491916627526,
			"height": 118.2666910432174,
			"seed": 1175730003,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "wU6WtXnl"
				},
				{
					"id": "QYX8zbi08ZqJDbmFDq0wE",
					"type": "arrow"
				},
				{
					"id": "qWOPCd5F8M4x_hjAU_Byp",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b0M"
		},
		{
			"type": "text",
			"version": 872,
			"versionNonce": 867389864,
			"isDeleted": false,
			"id": "wU6WtXnl",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2602.7161508958116,
			"y": 1557.5667851110788,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 184.0198516845703,
			"height": 50,
			"seed": 198694131,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Redis - stack per \nuser LRU",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "jra1MMAikiPC-gJj9GZCj",
			"originalText": "Redis - stack per \nuser LRU",
			"lineHeight": 1.25,
			"baseline": 42,
			"autoResize": true,
			"index": "b0N",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 186,
			"versionNonce": 128638120,
			"isDeleted": false,
			"id": "QYX8zbi08ZqJDbmFDq0wE",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2633.6588062877313,
			"y": 1413.9953565396504,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 30.717463635025524,
			"height": 94.28571428571422,
			"seed": 120173885,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740781276,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "wleRC_l8vq9nwHlTuExE2",
				"focus": -0.19053729216754398,
				"gap": 22.280991856588912
			},
			"endBinding": {
				"elementId": "jra1MMAikiPC-gJj9GZCj",
				"focus": -0.05126353815901966,
				"gap": 15.152368764105745
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					30.717463635025524,
					94.28571428571422
				]
			],
			"index": "b0O"
		},
		{
			"type": "arrow",
			"version": 50,
			"versionNonce": 712574888,
			"isDeleted": false,
			"id": "qWOPCd5F8M4x_hjAU_Byp",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2887.583175958869,
			"y": 1414.9477084276698,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 81.24504480971746,
			"height": 125.73640828708835,
			"seed": 1411650333,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ZcjGZhOb"
				}
			],
			"updated": 1756740781293,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "i5TlssxH7JjmtnCuEYUU0",
				"focus": -0.23187934554647824,
				"gap": 28.49117302237221
			},
			"endBinding": {
				"elementId": "jra1MMAikiPC-gJj9GZCj",
				"focus": 0.6088092540926001,
				"gap": 12.189639677462083
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-81.24504480971746,
					125.73640828708835
				]
			],
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b0P"
		},
		{
			"type": "text",
			"version": 13,
			"versionNonce": 1777151144,
			"isDeleted": false,
			"id": "ZcjGZhOb",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2804.785324436197,
			"y": 1464.3524848646116,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 92.7999267578125,
			"height": 25,
			"seed": 1387420029,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781210,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "cron daily",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "qWOPCd5F8M4x_hjAU_Byp",
			"originalText": "cron daily",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "b0Q",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 45,
			"versionNonce": 521212072,
			"isDeleted": false,
			"id": "c8jtJD7xUicnjt2L30LjF",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2972.3451824858603,
			"y": 888.2810126966434,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 1.904820033481883,
			"height": 74.28571428571433,
			"seed": 896421651,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "lz0D5YTA"
				}
			],
			"updated": 1756740781120,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "6mVULzuWQ14Hm8ow8tatz",
				"focus": -0.09655586766079546,
				"gap": 12.410340668613287
			},
			"endBinding": {
				"elementId": "X4oDtrSuZryJ_tCos31WC",
				"focus": 0.010522060082214612,
				"gap": 10.374834744759653
			},
			"lastCommittedPoint": null,
			"startArrowhead": "arrow",
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-1.904820033481883,
					74.28571428571433
				]
			],
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b0R"
		},
		{
			"type": "text",
			"version": 6,
			"versionNonce": 1593359272,
			"isDeleted": false,
			"id": "lz0D5YTA",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2955.8312490316193,
			"y": 912.9238698395005,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 31.459976196289062,
			"height": 25,
			"seed": 1959108243,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781120,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "cdc",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "c8jtJD7xUicnjt2L30LjF",
			"originalText": "cdc",
			"lineHeight": 1.25,
			"baseline": 17,
			"autoResize": true,
			"index": "b0S",
			"rawText": ""
		},
		{
			"type": "rectangle",
			"version": 214,
			"versionNonce": 1639936984,
			"isDeleted": false,
			"id": "B72HNUMssdDpj6fEDvviq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3127.7730912470247,
			"y": 486.3761970228153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 197.98866392517607,
			"height": 160,
			"seed": 2044252957,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "K1dSjRWq"
				},
				{
					"id": "nWv-AT7YbatJx9ub3PBYU",
					"type": "arrow"
				}
			],
			"updated": 1756740780619,
			"link": null,
			"locked": false,
			"customData": {
				"legacyTextWrap": true
			},
			"index": "b0T"
		},
		{
			"type": "text",
			"version": 311,
			"versionNonce": 667499944,
			"isDeleted": false,
			"id": "K1dSjRWq",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3139.9074988932066,
			"y": 491.3761970228153,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 173.7198486328125,
			"height": 150,
			"seed": 1881668957,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1756740781293,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "CRON - daily - \ncheck for invalid \nswipes. Invalid if \nswipe no longer \nmatches user \npreferences",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "B72HNUMssdDpj6fEDvviq",
			"originalText": "CRON - daily - \ncheck for invalid \nswipes. Invalid if \nswipe no longer \nmatches user \npreferences",
			"lineHeight": 1.25,
			"baseline": 142,
			"autoResize": true,
			"index": "b0U",
			"rawText": ""
		},
		{
			"type": "arrow",
			"version": 100,
			"versionNonce": 1512261800,
			"isDeleted": false,
			"id": "nWv-AT7YbatJx9ub3PBYU",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 3131.5932749146605,
			"y": 650.5183005509168,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 90.83087646840977,
			"height": 71.85319698382648,
			"seed": 1666392989,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1756740781307,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "B72HNUMssdDpj6fEDvviq",
				"focus": -0.05577466670860098,
				"gap": 12.000091552734375
			},
			"endBinding": {
				"elementId": "6mVULzuWQ14Hm8ow8tatz",
				"focus": -0.1399567245992772,
				"gap": 14.552024750976898
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-90.83087646840977,
					71.85319698382648
				]
			],
			"index": "b0V"
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 5,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"currentItemArrowType": "round",
		"currentItemFrameRole": null,
		"scrollX": 584.2436648544583,
		"scrollY": 574.3561632113051,
		"zoom": {
			"value": 0.354845
		},
		"currentItemRoundness": "round",
		"gridSize": 20,
		"gridStep": 5,
		"gridModeEnabled": false,
		"gridColor": {
			"Bold": "rgba(217, 217, 217, 0.5)",
			"Regular": "rgba(230, 230, 230, 0.5)"
		},
		"currentStrokeOptions": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true,
			"markerName": true,
			"markerEnabled": true
		},
		"objectsSnapModeEnabled": false,
		"activeTool": {
			"type": "selection",
			"customType": null,
			"locked": false,
			"fromSelection": false,
			"lastActiveTool": null
		}
	},
	"files": {}
}
```
%%