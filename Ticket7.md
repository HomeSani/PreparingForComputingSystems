## 1 Понятие дека. Реализвция на языках высокого уровня.

**Дек** — структура данных, представляющая из себя список элементов, в которой добавление новых элементов и удаление существующих производится с обоих концов. Эта структура поддерживает как FIFO, так и LIFO, поэтому на ней можно реализовать как стек, так и очередь.

Реализация на python:
```python
class Deque:
    def __init__(self):
        self.items = []

    def isEmpty(self):
        return self.items == []

    def addFront(self, item):
        self.items.append(item)

    def addRear(self, item):
        self.items.insert(0, item)

    def removeFront(self):
        return self.items.pop()

    def removeRear(self):
        return self.items.pop(0)

    def size(self):
        return len(self.items)
```

## 2 Массивы и множества.

Массивы — эффективные упорядоченные списки, которые используются для хранения информации в ситуациях, когда важен порядок следования элементов.

Множества отличаются от массивов в том плане, что в них не гарантируется порядок элементов.