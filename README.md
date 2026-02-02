# FUTURE_CS_03
Cyber Security Internship – Task 3: API Security Risk Analysis. Covers testing of public APIs using Postman/Insomnia, identification of insecure endpoints, authentication/authorization issues, and missing rate-limiting. Deliverable: professional API security risk analysis report documented in GitHub.

# API Security Risk Analysis – JSONPlaceholder

## 📌 Introduction
This project demonstrates an API Security Risk Analysis using the public demo API **[JSONPlaceholder](https://jsonplaceholder.typicode.com/)**.  
The goal is to identify common API security risks in a safe environment using **Postman** for testing.

---

## 🔧 Tools Used
- **Postman** – for sending HTTP requests and analyzing responses
- **GitHub** – for documentation and sharing findings

---

## 🎯 Scope of Analysis
Key risks analyzed in this project:
- ✔ Open or unauthenticated endpoints  
- ✔ Excessive data exposure in API responses  
- ✔ Weak or missing authentication tokens  
- ✔ Authorization issues (accessing other users’ data)  
- ✔ Missing rate limiting  
- ✔ Input validation issues  

---

## 📸 Evidence
Screenshots of Postman requests and responses are included in the `Screenshots/` folder:
- `GET /posts` → Open endpoint  
- `GET /users` → Excessive data exposure (emails, addresses, phones)  
- `GET /comments` → Data exposure (emails in comments)  
- `POST /posts` → Weak input validation (accepts any JSON)  
- `POST /posts` (malformed JSON) → Lack of strict validation  

---

## ⚠️ Risks Identified
| Endpoint | Risk | Severity | Suggested Remediation |
|----------|------|----------|------------------------|
| `GET /posts` | Open/unauthenticated endpoint | High | Require authentication |
| `GET /users` | Excessive data exposure (emails, addresses, phone numbers) | High | Restrict fields, mask sensitive data |
| `GET /comments` | Data exposure (emails in comments) | Medium | Limit exposure, anonymize data |
| `POST /posts` | Weak input validation (accepts any JSON, no auth) | Medium | Validate inputs, enforce authentication |
| `POST /posts` (malformed JSON) | Lack of strict validation | Low | Enforce schema validation |
| Any endpoint | Missing rate limiting | Medium | Implement rate limiting (e.g., 100 requests/minute) |
| Any endpoint | Authorization issues | High | Enforce authorization checks |

---

## 📂 Repository Structure
