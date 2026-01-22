# Postman API Fundamentals – Skill Check

This repository contains a **Postman Collection** created to complete the **Postman API Fundamentals Student Expert – Skill Check**.

The goal of this activity is to demonstrate core API testing skills using Postman, including requests, variables, authorization, and test scripts.

---

## 📌 What This Collection Includes

- A **POST request** named **`skill check`**
- Organized inside the folder **`delete a book request`**
- Uses the **Postman Echo API** to reflect sent data
- Query parameters, request body, authorization, and test scripts configured

---

## 🧪 Skills Demonstrated

- Creating and organizing Postman requests
- Using **Query Parameters**
- Defining and reusing **Collection Variables**
- Applying **API Key Authorization**
- Sending **JSON request bodies**
- Writing **Post-response test scripts**
- Setting variables dynamically from API responses

---

## 🔧 Request Details

### Endpoint
```
POST {{skillcheckBaseUrl}}/post
```

### Query Parameter
```
movieName = Inception
```

### Authorization
- Type: **API Key**
- Key: `student-expert`
- Value: `skillcheck`
- Added to: **Header**

### Request Body (JSON)
```json
{
  "actorName": "Leonardo DiCaprio"
}
```

---

## 🧠 Post-response Script

After the request is sent, the response is used to automatically save the actor name as a **collection variable**:

```javascript
const responseData = pm.response.json();

pm.collectionVariables.set(
  "favoriteActor",
  responseData.json.actorName
);
```

This sets the variable:
```
favoriteActor = Leonardo DiCaprio
```

---

## 🌐 Collection Variables

| Variable Name | Value |
|--------------|-------|
| skillcheckBaseUrl | https://postman-echo.com |
| favoriteActor | Set dynamically from response |

---

## 📥 How to Use

1. Open **Postman**
2. Click **Import**
3. Import the file:
   ```
   Postman_Skill_Check_Collection.json
   ```
4. Open the request **skill check**
5. Click **Send**
6. Verify the response and confirm the variable `favoriteActor` is created

---

## ✅ Expected Result

- Request returns **200 OK**
- Response echoes the sent data
- Collection variable `favoriteActor` is correctly set
- Collection passes the **Postman Collection Test (28/28)**

---

## 🎓 Certification Context

This collection was built as part of the **Postman API Fundamentals Student Expert Certification**, demonstrating practical API testing knowledge suitable for:

- QA / Software Tester roles
- Backend or API-focused positions
- Entry-level and junior developer portfolios

---

## 👤 Author

Created by **Miguel Souza**  
Software Engineering Student  
Focused on **QA, API Testing, and Software Quality**

