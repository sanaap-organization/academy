[⬅ Back](./main.md)
---

## 3. Polymorphism: جایگزینی شرط های مبتنی بر نوع

اگر تصمیم گیری بر اساس نوع آبجکت است، Polymorphism راهکار قدرتمندی است.

### مثال

**if روی نوع:**
```python
def calculate_area(shape):
    if isinstance(shape, Circle):
        return 3.14 * shape.radius ** 2
    elif isinstance(shape, Square):
        return shape.side ** 2
```

**روش OOP:**
```python
class Shape:
    def area(self):
        raise NotImplementedError

class Circle(Shape):
    def area(self):
        return 3.14 * self.radius ** 2

class Square(Shape):
    def area(self):
        return self.side ** 2
```

**حالا کافی است**
```python
shape.area()
```

**مزایا:**
- بدون هیچ شرط اضافی