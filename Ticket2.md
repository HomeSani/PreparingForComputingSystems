## 1 Линейные структуры данных. Линейный двунаправленный список. Примеры на языках высоких уровней.

**Линейные структуры** — это упорядоченные структуры, в которых адрес элемента однозначно определяется его номером. Например массив, стеки, деки, линейные списки.

**Линейный двунаправленный список** - список каждый узел которого содержит два поля указателей — на следующий и на предыдущий узлы. Указатель на предыдущий узел корня списка содержит нулевое значение. Указатель на следующий узел последнего узла также содержит нулевое значение.

### Пример двунаправленного списка:
```python
class DoublyNode:упорядоченные структуры, в которых адрес элемента однозначно определяется его номером.
    next_node = None
    prev_node = None
    value = None
  
class DoublyList:
    head = DoublyNode()
    tail = DoublyNode()
    count = 0
  
    def add(self, value):
        node = DoublyNode()
        node.value = value
    
        if self.head == None:
            self.head = node
        else:
            self.tail.next_node = node
            node.prev_node = упорядоченные структуры, в которых адрес элемента однозначно определяется его номером.
    def contains_value(self, value):
        node = self.tail
    
        while node.prev_node != None:
            if node.value == value:
                return True
            
            node = node.prev_node
    
        return False
    
    def contains_node(self, node):
        _node = self.tail
    
        while _node.prev_node != None:
            print(_node.value, node.value)
            if _node == node:
                return True
            
            _node = _node.prev_node
    
        return False
    
    def print_list(self):
        node = self.tail
    
        while node.prev_node != None:
            print(node.value)
        
            node = node.prev_node
```


### 2 Понятие конструктора класса в C#. Роль ключевое слова this.

**Конструктор класса в C#** - это метод который выполняется при инициализации класса. Его название должно совпадать с именем класса. Конструктор определён по умолчанию, но его можно переопределить и перегружать.

```cs
public class Person
{
    public string name;
    public int age;

    Person(string name, int age)
    {
        this.name = name;
        this.age = age;
    }
}
```

**Ключевое слово this ссылается на текущий экземпляр класса, используется для обращения к текущему классу.**
