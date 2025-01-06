

# wick.fun







## Authors

- [@veracitelol](https://www.github.com/veracitelol)
[![Discord Presence](https://lanyard.cnrad.dev/api/1295320092455862275?bg=ff1c64&showDisplayName=true)](https://discord.com/users/1295320092455862275)
##


## FYI

 -  this is just a test project made by @aidenchrist on discord


![Logo](https://r2.strap.lol/rip.png.PNG)




---

# API Reference

## Authentication

### Register a new user  
**POST** `/api/auth/register`  
**Body:**  
`{ "name": "string", "email": "string", "password": "string" }`  
**Response:**  
`{ "user": { "id": "string", "name": "string", "email": "string" } }`

### Login  
**POST** `/api/auth/login`  
**Body:**  
`{ "email": "string", "password": "string" }`  
**Response:**  
`{ "token": "string", "user": { "id": "string", "name": "string", "email": "string" } }`

### Get current user  
**GET** `/api/auth/me`  
**Headers:**  
`Authorization: Bearer <token>`  
**Response:**  
`{ "user": { "id": "string", "name": "string", "email": "string", "avatar": "string" } }`

## Pins

### Get all pins  
**GET** `/api/pins`  
**Response:**  
`[{ "_id": "string", "title": "string", "description": "string", "imageUrl": "string", "creator": { "name": "string", "avatar": "string" } }]`

### Create a new pin  
**POST** `/api/pins`  
**Headers:**  
`Authorization: Bearer <token>`  
**Body:**  
`{ "title": "string", "description": "string", "imageUrl": "string" }`  
**Response:**  
`{ "_id": "string", "title": "string", "description": "string", "imageUrl": "string", "creator": "string" }`

### Get a specific pin  
**GET** `/api/pins/:id`  
**Response:**  
`{ "_id": "string", "title": "string", "description": "string", "imageUrl": "string", "creator": { "name": "string", "avatar": "string" } }`

### Update a pin  
**PUT** `/api/pins/:id`  
**Headers:**  
`Authorization: Bearer <token>`  
**Body:**  
`{ "title": "string", "description": "string", "imageUrl": "string" }`  
**Response:**  
`{ "_id": "string", "title": "string", "description": "string", "imageUrl": "string", "creator": "string" }`

### Delete a pin  
**DELETE** `/api/pins/:id`  
**Headers:**  
`Authorization: Bearer <token>`  
**Response:**  
`{ "message": "Pin deleted successfully" }`

## Error Responses
- **400 Bad Request:** Malformed request or missing fields  
- **401 Unauthorized:** Invalid token or not authenticated  
- **403 Forbidden:** Action not allowed  
- **404 Not Found:** Resource not found  
- **500 Internal Server Error:** Unexpected server error  

**Note:** All authenticated routes require a valid JWT token in the `Authorization` header.

--- 


