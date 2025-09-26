## **Adding and Validating Users in DB via Bruno – User Registration Boilerplate**

This live practical session focuses on planning and documenting a **secure user registration feature**. You’ll define a Mongoose schema with validations, plan how password hashing will work using `bcrypt`, and prepare to test the `/register` API using **Bruno**.

Instead of a hospital system, we’ll build the foundations of a **User Authentication System**.

### **1. Scenario Overview**

You're developing the backend for a **user registration system**. The system should allow:

- Creating a new user account
- Validating user inputs (e.g., email format, password length)
- Hashing the user’s password before saving it

Each user record includes:

- `name` (String, required)
- `email` (String, required, must be valid format)
- `password` (String, required, minimum length 6)

### **2. Plan Your API Endpoint**

Define the route needed to handle user registration:

| Endpoint         | Description         |
| ---------------- | ------------------- |
| POST `/register` | Register a new user |

Use RESTful standards and follow secure backend design practices.

### **3. Choose the Right Mongoose + Security Methods**

Use the appropriate Mongoose and bcrypt methods to build a secure flow:

| Task                   | Method or Tool                      |
| ---------------------- | ----------------------------------- |
| Create a new user      | `User.create()`                     |
| Hash password          | `bcrypt.hash(password, saltRounds)` |
| Run logic before save  | `UserSchema.pre('save', async fn)`  |
| Validate schema fields | Mongoose validators                 |

---

### **4. Testing with API Client**

Use **Bruno** or **Postman** to simulate registration scenarios:

- **POST**: Send
  `{"name": "Aarav", "email": "aarav@email.com", "password": "securepass"}`
  and expect a **201 Created** response
- **Validation Test**: Send missing or invalid fields
  (e.g., no email or password too short) and expect **400 Bad Request**
- **Hash Check**: Confirm password stored in DB is hashed (not in plain text)

### **5. Repository and Setup Instructions**

**Fork the StackBlitz Project:**

**Push to GitHub:**

```bash
git init
git remote add origin <your_repo_url>
git add .
git commit -m "Planned user registration flow with validation and hashing"
git push -u origin main
```

### **6. Submission Format**

Submit a **PDF** containing:

- GitHub repository link
- Google Drive link to your explanation video (set visibility to `kalvium.community`)
- A short note explaining your plan and logic

**Example Naming Format:**
`user_registration_<yourname>.pdf`

**Example Content:**

- GitHub: `https://github.com/<your_username>/user_registration`
- Video: Google Drive link
- Note: “Planned secure user registration flow with schema validation, password hashing, and test cases in Bruno.”
