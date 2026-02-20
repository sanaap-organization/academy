[⬅ Back](./main.md)
---

## 5. Match-Case (Python 3.10+)

Python 3.10+ امکان استفاده از match-case را می دهد که خواناتر از زنجیره if-elif است.

```python
def handle_status(status):
    match status:
        case "pending":
            ...
        case "approved":
            ...
        case "rejected":
            ...
```