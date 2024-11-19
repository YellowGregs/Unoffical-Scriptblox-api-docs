# cool...

These are the unofficial ScriptBlox API docs.  
- Have fun reading / using the ScriptBlox API.

---

# **Note:**

- Everything that is in **brackets** (and not commented) refers to JSON data.
- If you're making a request and it doesn't work, **try adding the Authorization header** with your token.
- If you need help using JSON data in Python, here’s an example:
- **Token Expiration**: I don't know if the Tokens can be expire, but If you encounter authentication errors, you may need to retrieve a new token.

---

### **Example in Python:**

```python
import requests

# This is a Example data you want to send in your request
jsonData = {"email":"testmail@gmail.com"}

headers = {"Authorization":"your-token-here"}  # Replace 'your-token-here' with your token

requests.post(url="https://scriptblox.com/api/user/reset-password", json=jsonData, headers=headers)
```

# **ScriptBlox Token**

If you need to authenticate your requests to the ScriptBlox API, you will need to retrieve your **ScriptBlox token**. Here’s how you can find it:

### **Steps to Find the Token**

1. **Go to ScriptBlox Website**:
   - Visit [ScriptBlox](https://scriptblox.com) and log in to your account.

2. **Open Developer Tools**:
   - Press **F12** on your keyboard or right-click anywhere on the page and select **Inspect** (or **Inspect Element**).

3. **Navigate to the Application Tab**:
   - Once the Developer Tools panel is open, click on the **Application** tab at the top.

4. **Find Cookies**:
   - In the left sidebar, under the **Storage** section, click on **Cookies**. This will show all cookies for the ScriptBlox website (`https://scriptblox.com`).

5. **Locate the Token**:
   - In the list of cookies, search for the `token` entry. The value next to it is your token. It may look something like `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjYzODM5YjA3ZTk4MjU1MjRkMDFjOTN`. (this is just a exmaple)

6. **Copy the Token**:
   - Copy the token value. You can now use this token to authenticate your requests to the API.

---

# ⚠️⚠️ **Important**:

- **Keep Your Token Secure**: Your token is sensitive and should not be shared with others or exposed publicly.
