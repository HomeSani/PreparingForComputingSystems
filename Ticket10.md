## 1 Циклические списки. Циклический однонаправленный список. Его реализация.

**Циклический (кольцевой) список** – это структура данных, представляющая собой последовательность элементов, последний элемент которой содержит указатель на первый элемент списка, а первый (в случае двунаправленного списка) – на последний.

**Циклический однонаправленный список** похож на линейный однонаправленный список, но его последний элемент содержит указатель, связывающий его с первым элементом

Реализация:
```python
class ListNode:
    def __init__(self, value):
        self.value = value
        self.next_node = None

class List:
    head = None

    def add(self, value):
        node = ListNode(value)

        if not self.head:
            self.head = node
            
            return

        last_node = self.head

        while (last_node.next_node):
            last_node = last_node.next_node

        last_node.next_node = node

    def pprint(self):
        node = self.head

        while node.next_node:
            print(node)

            node = node.next_node
```

## 2 Понятие ключевого слова static.

**Static** – это ключевое слово, которое широко применяется в программировании, включая Си Шарп. Иногда нужно определять член класса, который будет применяться независим от всех остальных объектов этого класса. Доступ к члену организовывается путем объекта класса. Но есть и другое решение. В программировании допускается создание отдельного члена класса без ссылок на конкретный экземпляр объекта. В этом помогает ключевое слово static.

Если члены этого же класса объявляются в качестве статических, они становятся доступными до создания разных объектов своего класса без ссылок на objects. Существует множество различных методов рассматриваемого типа. Наиболее распространенный – Main(). Он объявляется статическим из-за того, что должен вызываться имеющейся системой при запуске того или иного приложения.

Для использования статическим членом за пределами класса, нужно прописать class name с оператором-точкой. Никакого создания объекта не потребуется. Члены типа static оказываются доступными не по ссылкам, а по именам класса.

Говоря о переменных, можно отметить, что static – это глобальные переменные по своему существу. Если объекты будут созданы в своем же классе, копии переменных статического типа не образовываются. Вместо этого все экземпляры будут использованы совместно с одной и той же переменной типа static.