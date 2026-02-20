[⬅ Back](./main.md)
---

## 6. Rule Engine Style: مدیریت شرط های ترکیبی

اگر چند شرط ترکیبی داریم، می توانیم هر شرط را به تابع مستقل تبدیل کنیم و با all یا any بررسی کنیم.

```python
def is_active(user):
    return user.is_active

def is_adult(user):
    return user.age > 18

def is_not_banned(user):
    return not user.is_banned

RULES = [is_active, is_adult, is_not_banned]

def can_login(user):
    return all(rule(user) for rule in RULES)
```

**مزایا:**
- قابل تست جداگانه
- توسعه پذیر برای قوانین جدید