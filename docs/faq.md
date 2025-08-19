# FAQ – SimpleChat API

This page answers the most common questions about using the **SimpleChat API**.

---

## 🔑 Authentication & API Key

### How do I get an API key?
1. Sign up or log in to your SimpleChat account.  
2. Go to your **API Dashboard**.  
3. Click **Generate API Key**.  
4. Copy and securely store your API key.

!!! note "Security Tip"
    Never share your API key publicly or commit it to version control. Treat it like a password.

---

### What if my API key is lost or compromised?
- Go to your **API Dashboard**.  
- Revoke the old key and generate a new one.  
- Update your applications with the new key immediately.

---

## ⚡ Rate Limits

### How many API requests can I make?
- Free Tier: 100 requests per hour  
- Pro Tier: 1000 requests per hour  

!!! warning "Rate Limit Exceeded"
    If you exceed the limit, your API will return **HTTP 429 Too Many Requests**.  
    Implement **retry logic** or upgrade your plan.

---

## 🛠️ Common Errors

### 401 Unauthorized
- Cause: Missing or invalid API key.  
- Solution: Verify your key and ensure it is included in the header:

```http
Authorization: Bearer <YOUR_API_KEY>
```

### 404 Not Found
- Cause: Endpoint or message ID does not exist.  
- Solution: Double-check the URL and parameters.

### 500 Internal Server Error
- Cause: Server-side issue.  
- Solution: Retry after a few seconds. Contact support if it persists.

---

## 💡 Tips & Best Practices

- Always check the **status code** before processing data.  
- Use **GET /messages** to confirm updates or deletions.  
- Keep your API keys secure and **rotate them periodically**.  
- Implement **error handling** for 401, 404, and 429 codes.

---

## ✅ Summary

- FAQs cover **authentication, rate limits, and errors**.  
- Use callouts to highlight **important tips and warnings**.  
- Following these guidelines ensures **smooth integration** with SimpleChat API.
