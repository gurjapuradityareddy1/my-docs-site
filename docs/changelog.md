# Changelog – SimpleChat API

Keep track of all changes, updates, and improvements to the **SimpleChat API**.

---

## 📅 Version 1.2.0 – 2025-08-15

### Added
- New endpoint: `GET /messages/{id}` to fetch a single message by ID  
- Support for rich text formatting in messages  

### Fixed
- Bug where `PUT /messages/{id}` sometimes ignored updates  
- Error handling for invalid API keys  

### Improved
- Enhanced response times for `GET /messages`  
- Updated Python examples for better readability

---

## 📅 Version 1.1.0 – 2025-07-20

### Added
- `DELETE /messages/{id}` endpoint to remove messages  
- Rate limit info added to API responses  
- Example workflows for creating and updating messages  

### Fixed
- JSON formatting issue in `POST /messages` response  
- Minor typo in authentication header documentation

---

## 📅 Version 1.0.0 – 2025-06-01

### Initial Release
- Core endpoints: `GET /messages`, `POST /messages`, `PUT /messages/{id}`  
- Authentication via API key  
- Basic error codes and sample responses  
- Getting Started and API Reference documentation pages

---

### ✅ Summary

- **Version 1.0.0** – Initial launch  
- **Version 1.1.0** – Added delete endpoint, improved examples  
- **Version 1.2.0** – Added single message fetch, rich text support, bug fixes  

!!! tip "Pro Tip"
    Always check the **latest version** before using the API to ensure you have access to all new features and fixes.
