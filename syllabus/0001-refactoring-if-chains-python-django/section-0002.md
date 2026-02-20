[⬅ Back](./main.md)
---

## 2. Strategy Pattern: مدیریت رفتارهای متفاوت

زمانی که شرایط مختلف با رفتار متفاوت همراه هستند، Strategy Pattern گزینه ای ایده آل است.

### مثال

**روش سنتی با if:**
```python
def pay(order, method):
    if method == "bank":
        ...
    elif method == "stripe":
        ...
    elif method == "wallet":
        ...
```

**روش Strategy:**
```python
class PaymentStrategy:
    def pay(self, order):
        raise NotImplementedError

class BankPayment(PaymentStrategy):
    def pay(self, order):
        ...

class StripePayment(PaymentStrategy):
    def pay(self, order):
        ...

class WalletPayment(PaymentStrategy):
    def pay(self, order):
        ...
```

**Factory ساده:**
```python
PAYMENT_METHODS = {
    "bank": BankPayment(),
    "stripe": StripePayment(),
    "wallet": WalletPayment(),
}

def process_payment(method: str, order):
    return PAYMENT_METHODS[method].pay(order)
```

**مزایا:**
- جداسازی منطق بر اساس رفتار
- قابل تست و توسعه