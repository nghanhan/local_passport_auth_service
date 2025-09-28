# Local Passport Authentication (LAB: Security in NodeJS)

## 1. Cách chạy dự án

1. Cài đặt thư viện
Chạy lệnh sau để cài tất cả dependencies:
```bash
npm install
```
2. Khởi động MongoDB
3. Start servers:
```bash
node app.js
```

## Endpoints & How to test (POSTMAN)
### 1. Register
POST `http://localhost:3000/auth/register`
Body JSON:
```json
{ "username": "admin", "password": "12345" }
```
Expected: User registered successfully.  
![register](public/results/register.png)
Fail case: "error": "E11000 duplicate key error collection: ... "
![register_fail](public/results/register_fail.png)

### 2. Login
POST `http://localhost:3000/auth/login`
#### Expected:
Body JSON:
```json
{ "username": "admin", "password": "12345" }
``` 
![login](public/results/login.png)
#### Fail:
Body JSON:
```json
{ "username": "admin", "password": "123445" }
```
![login_fail](public/results/login_fail.png)

### 3. profile
GET `http://localhost:3000/auth/profile`
Expected: Profile data.  
![profile](public/results/profile.png)
Fail: Not authenticated
![profile_fail](public/results/profile_fail.png)

### 4. logout
GET `http://localhost:3000/auth/logout`

Expected: Logged in successfully.

![logout](public/results/logout.png)
---

(Tất cả hình ảnh trong `public/results/`)

---