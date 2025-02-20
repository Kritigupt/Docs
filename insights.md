# CRUD APIs For Inkyst Insights Page

## ✅ Create an Insight

Users can create inkyst insights with image uploads.


### API Endpoint

**Method:** `POST`  

**URL:** `http://localhost:8086/api/v1/insights`


### Request Headers

```plaintext

Content-Type: multipart/form-data
```
Request Example

```bash

curl --location 'http://localhost:8086/api/v1/insights' \
--header 'Cookie: JSESSIONID=BD09D22736E3ADE106D1BA2DB7B53E3F' \
--form 'title="Testing new"' \
--form 'file=@"/C:/Users/kriti/Downloads/buk.jpg"' \
--form 'description="description new is the"' \
--form 'userId="12345"'
```
```
| Parameter       | Type      | Description                                   |
|-----------------|-----------|-----------------------------------------------|
| `title`         | String    | Title of the insight(Size between 5 to 50)    |
| `description`   | String    | Description of the insight(Min=10 , Max=500)  |
| `image`         | File[]    | Image file related to particular insight      |
| `insightId`     | String    | Id of the insight                             |
| `userId`        | String    | Id of the user who has created the insight   |                                         
```

###  🌐 Response Structure 
```json
{
    "status": "CREATED",
    "message": "Insight created successfully",
    "data": {
        "insightId": "67b78ec6919f0e02eaba4468",
        "title": "Testing new",
        "fileUrl": "https://storage.cloud.google.com/inkyst_collection_bucket/insights/files/89a93dea-d53f-4b13-a436-ba36e83ec5d9-buk.jpg",
        "description": "description new is the",
        "userId": "12345"
    }
}
```

## ✅ Get an Insight by its ID

Users can get particular insight using insightId


### API Endpoint

**Method:** `GET`  

**URL:** `http://localhost:8086/api/v1/insights/{insightId}`

Request Example
``` bash
curl --location 'http://localhost:8086/api/v1/insights/67b78ec6919f0e02eaba4468' \
--header 'Cookie: JSESSIONID=BD09D22736E3ADE106D1BA2DB7B53E3F'
```

###  🌐 Response Structure 
```json
{
    "status": "OK",
    "message": "Insight fetched successfully",
    "data": {
        "insightId": "67b78ec6919f0e02eaba4468",
        "title": "Testing new",
        "fileUrl": "https://storage.cloud.google.com/inkyst_collection_bucket/insights/files/89a93dea-d53f-4b13-a436-ba36e83ec5d9-buk.jpg",
        "description": "description new is the",
        "userId": "12345"
    }
}
```


