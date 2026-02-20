[⬅ Back](./main.md)
---

## 4. Guard Clauses: کاهش تو در تویی

برای شرایط validation، استفاده از guard clauses باعث حذف if های تو در تو می شود.

### مثال

**وجود if های تو در تو**
```python
def create_user(data):
    if data:
        if "email" in data:
            if data["email"].endswith("@gmail.com"):
                return User.objects.create(...)
```

**بعد از اصلاح**
```python
def create_user(data):
    if not data:
        raise ValueError("No data")

    email = data.get("email")
    if not email:
        raise ValueError("Email required")

    if not email.endswith("@gmail.com"):
        raise ValueError("Invalid email")

    return User.objects.create(...)
```

**مزایا:**
- خوانایی بالا
- جلوگیری از if/else hell