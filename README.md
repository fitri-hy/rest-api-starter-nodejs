# 🚀 Rest-API Starter Kit

Starter Kit for building modern RESTful APIs with scalable 🏗️, modular 🧩, and secure 🔐 architecture. Suitable for use as an initial foundation for developing small to large scale backend applications, equipped with various built-in features that are ready to use 🧰 and easy to develop further 🚧.

---

## 🚀 Built-in Features

- ✅ Authentication
- 🧼 Input Validation & Sanitation
- 🔐 Password Hashing
- 🔑 JWT Token Auth
- 🔄 Database Switching (MySQL / PostgreSQL)
- 🧩 Modular
- 📦 ORM Sequelize
- 🧯 Handling errors
- 🏗️ Scalable Project Structure
- 🛡️ Rate Limiting
- 📛 Security Headers
- ⚡ Redis Caching
- ❤️ Health Check & Monitoring
- 🐂 Asynchronous Task Handling (Bull Queue)
- 📥 Upload File Handlers
- 🔁 Graceful Shutdown
- 🎛️ Request Profiling
- 🔒 HTTP Compression (gzip/brotli)

---

## 📊 Status Monitoring

#### Endpoint

```
GET http://localhost:5000/status
```

---

## 🐂 Task Handling

#### Endpoint

```
POST http://localhost:5000/api/v1/tasks/add
```

#### Header Request (If using ApiKey)

| Key             | Value                           |
|:----------------|:--------------------------------|
| x-api-key       | my_secret_api_key               |


---

## 🧠 Redis Caching

#### Endpoint

```
GET http://localhost:5000/api/v1/data/:key
```

#### Header Request (If using ApiKey)

| Key             | Value                           |
|:----------------|:--------------------------------|
| x-api-key       | my_secret_api_key               |


---

## 👤 Example Case (Login, Register, Get User)

### Register

#### Endpoint
```
POST http://localhost:5000/api/v1/users/register
```

#### Header Request (If using ApiKey)

| Key             | Value                           |
|:----------------|:--------------------------------|
| x-api-key       | my_secret_api_key               |

#### Body Request

```
{
  "name": "John Doe",
  "email": "johndoe@example.com",
  "password": "securepassword"
}
```

#### Response

```
{
   "id": 1,
   "name": "John Doe",
   "email": "johndoe@example.com"
}
```

### Login

#### Endpoint

```
POST http://localhost:5000/api/v1/users/login
```

#### Header Request (If using ApiKey)

| Key             | Value                           |
|:----------------|:--------------------------------|
| x-api-key       | my_secret_api_key               |


#### Body Request

```
{
  "email": "johndoe@example.com",
  "password": "securepassword"
}
```

#### Response

```
{
  "token": "your_jwt_token_here"
}
```

### Get Users

#### Endpoint

```
GET http://localhost:5000/api/v1/users
```

#### Header Request (If using ApiKey)

| Key             | Value                           |
|:----------------|:--------------------------------|
| x-api-key       | my_secret_api_key               |


#### Header Authorization:

| Key             | Value                           |
|:----------------|:--------------------------------|
| Authorization   | Bearer `<your_jwt_token_here>`  |

#### Response

```
[
  {
    "id": 1,
    "name": "John Doe",
    "email": "johndoe@example.com"
  }
]
```

---

## File Upload
#### Endpoint

```
POST http://localhost:5000/api/v1/upload/:folderName

Default Location: public/uploads
```

#### Header Request (If using ApiKey)

| Key             | Value                           |
|:----------------|:--------------------------------|
| x-api-key       | my_secret_api_key               |


#### Body Request (form-data)

| Key           | Type		| Value                    |
|:--------------|:----------|:-------------------------|
| file       	| file		| Select File         |


#### Response

```
{
    "message": "File uploaded successfully",
    "file": {
        "fieldname": "file",
        "originalname": "your-image.jpeg",
        "encoding": "7bit",
        "mimetype": "image/jpeg",
        "destination": "public/uploads/",
        "filename": "1744786296980-815431101.jpeg",
        "path": "public\\uploads\\1744786296980-815431101.jpeg",
        "size": 582884
    }
}
```

---

## 🗂️ Folder Structure

```
rest-api-starter/
├── src/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── service/
│   └── utils/
├── .env
├── .gitignore
├── package.json
└── app.js
```