[⬅ Back](./main.md)
---

## 1. Dictionary Dispatch: ساده و خوانا

یکی از ساده ترین روش ها برای جایگزینی چندین شرط بر اساس مقدار یک متغیر، استفاده از **دیکشنری و lambdas** است.  

### مثال

**کد با چندین if:**
```python
def calculate_discount(user_type, price):
    if user_type == "regular":
        return price * 0.95
    elif user_type == "vip":
        return price * 0.85
    elif user_type == "staff":
        return price * 0.5
    elif user_type == "blacklist":
        return 0
```

**کد تمیزتر با Dictionary Dispatch:**
```python
DISCOUNT_MAP = {
    "regular": lambda p: p * 0.95,
    "vip": lambda p: p * 0.85,
    "staff": lambda p: p * 0.5,
    "blacklist": lambda p: 0,
}

def calculate_discount(user_type: str, price: float) -> float:
    return DISCOUNT_MAP.get(user_type, lambda p: p)(price)
```

**مزایا:**
- خوانایی بالا
- اضافه کردن حالت های جدید بسیار ساده
- بدون زنجیره طولانی شرط ها