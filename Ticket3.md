## 1 Поддержка полиморфизма в C#(virtual, override)

**Полиморфизм** — это способность обьекта использовать методы производного класса, который не существует на момент создания базового.

Те методы и свойства, которые мы хотим сделать доступными для переопределения, в базовом классе помечается модификатором virtual. Такие методы и свойства называют виртуальными.

А чтобы переопределить метод в классе-наследнике, этот метод определяется с модификатором override.

```cs
class Person
{
    public string name;

    public virtual void Print()
    {
        Console.WriteLine("Name - " + name);
    }
}

class Employee : Person
{
    public string companyName;

    public override Print() : base(name)
    {
        Console.WriteLine($"{name} working in {companyName}");
    }
}
```

## 2 Циклические списки. Циклический двунаправленный список. Примеры реализаций.

**Циклический (кольцевой) список** – это структура данных, представляющая собой последовательность элементов, последний элемент которой содержит указатель на первый элемент списка, а первый (в случае двунаправленного списка) – на последний.

```python
from time import sleep


class DoublyRingNode:
    next_node = None
    prev_node = None
    value = None


class DoublyRingList:
    head = DoublyRingNode()
    count = 0
  
    def add(self, value):
        node = DoublyRingNode()
        node.value = value

        node.next_node = self.head
    
        if self.head:
            self.head.prev_node = node
        
        self.head = node
        self.count += 1

    def print_list(self):
        node = self.head
    
        while node.next_node is not None:
            print(node)

            node = node.next_node
            sleep(1)
```