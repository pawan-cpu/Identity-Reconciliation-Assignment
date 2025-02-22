# FastAPI Contact Identification API

## **Project Setup & Deployment Guide**

### **1. Local Setup (VS Code & Python)**

#### **Prerequisites:**
- Python 3.12 installed
- `pip` installed
- VS Code with Python extension

#### **Steps to Run Locally:**
```sh
# Clone the repository
git clone <repo-url>
cd <repo-folder>

# Install dependencies
pip install -r requirements.txt

# Run the application
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

#### **Run Tests:**
```sh
pytest test_identity_reconciliation.py
```

---

### **2. Running on GitHub Codespaces**

#### **Steps to Set Up:**
1. Open the repository in GitHub.
2. Click on `<> Code` > `Codespaces` > `Create codespace on main`.
3. Once the environment is ready, open a terminal and run:
   ```sh
   pip install -r requirements.txt
   uvicorn main:app --host 0.0.0.0 --port 8000 --reload
   ```
4. Use `pytest test_identity_reconciliation.py` to run tests.

---

### **3. Running with Docker**

#### **Steps to Run in Docker:**
```sh
# Build the Docker image
docker build -t fastapi-contact-api .

# Run the container
docker run -p 8000:8000 fastapi-contact-api
```

#### **Access API:**
Once running, open `http://localhost:8000/docs` in a browser to access the FastAPI interactive docs.

---

### **4. API Endpoints**
#### **POST /identify**
- **Description:** Identifies contacts and links primary/secondary accounts.
- **Payload Example:**
```json
{
    "email": "test@example.com",
    "phoneNumber": "1234567890"
}
```
- **Response Example:**
```json
{
    "primaryContactId": 1,
    "emails": ["test@example.com"],
    "phoneNumbers": ["1234567890"],
    "secondaryContactIds": []
}
```

---

### **5. Notes**
- Make sure `sqlite3` is installed if using a database.
- Modify `main.py` if additional configurations are needed.

---

**Author:** Pawan Kumar
