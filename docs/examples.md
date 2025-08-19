# Examples & Tutorials

This page provides step-by-step examples of how to use the **SimpleChat API** for common tasks.

---

## 1️⃣ Create Your First Message

**Goal:** Send a message from one user to another.

!!! note "Before You Start"
    Make sure you have your **API key** and have set up your account in the API Dashboard.

**Step 1: Prepare the Request**

```python
import requests

api_key = "YOUR_API_KEY"
url = "https://api.simplechat.example.com/messages"

payload = {
    "to": "bob",
    "message": "Hello Bob! This is my first message."
}

headers = {
    "Authorization": f"Bearer {api_key}",
    "Content-Type": "application/json"
}
```

**Step 2: Send the Request**

```python
response = requests.post(url, headers=headers, json=payload)
print(response.json())
```

**Sample Response:**

```json
{
    "id": 1,
    "from": "alice",
    "to": "bob",
    "message": "Hello Bob! This is my first message.",
    "timestamp": "2025-08-19T10:00:00Z"
}
```

---

## 2️⃣ List All Messages

**Goal:** Fetch all messages in your account.

```python
response = requests.get("https://api.simplechat.example.com/messages", headers=headers)
messages = response.json()
for msg in messages:
    print(f"{msg['from']} → {msg['to']}: {msg['message']}")
```

**Sample Output:**

```
alice → bob: Hello Bob! This is my first message.
bob → alice: Hey Alice! Got your message.
```

---

## 3️⃣ Update a Message

**Goal:** Modify the content of an existing message.

```python
message_id = 1
payload = {"message": "Hello Bob! Edited message content."}

response = requests.put(f"https://api.simplechat.example.com/messages/{message_id}", headers=headers, json=payload)
print(response.json())
```

**Sample Response:**

```json
{
    "id": 1,
    "from": "alice",
    "to": "bob",
    "message": "Hello Bob! Edited message content.",
    "timestamp": "2025-08-19T10:05:00Z"
}
```

---

## 4️⃣ Delete a Message

**Goal:** Remove a message by its ID.

```python
message_id = 1
response = requests.delete(f"https://api.simplechat.example.com/messages/{message_id}", headers=headers)
print(response.status_code)  # 204 = Success
```

!!! tip "Good Practice"
    Always confirm deletion by fetching the list of messages again. Handle `404 Not Found` if the message ID does not exist.

---

## 5️⃣ Real-World Workflow

**Scenario:** Alice sends a message → Bob receives → Bob replies → Alice updates her original message → Alice deletes an old message.

1. Send a message (`POST /messages`)  
2. List messages (`GET /messages`)  
3. Update a message (`PUT /messages/{id}`)  
4. Delete a message (`DELETE /messages/{id}`)  

![Message Workflow](images/message-workflow.png)

---

## ✅ Summary

- Step-by-step examples show **how to send, list, update, and delete messages**.  
- Use **callouts and tips** to make your workflow robust.  
- Include **visual aids** for clarity.  

