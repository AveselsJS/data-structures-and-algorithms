# Структуры данных и алгоритмы

## Big O

Big O являет собой математический принцип определяющий количество операций необходимых доя достижения результата. 
Big O исчесляется в количестве операций n.

Варианты Big O <br/>

| Формат Big O | Количество операций |
| :----------: | :-----------------: |
| Big O(1) | 1 | 
| Big O log(n) | ~ 3 |
| Big 0(n) | 10 | 
| Big 0(n^2) | 100 | 
| Big 0(2^n) | 1024 |
| Big 0(n!) | 3 628 800 |

При подходящем выборе структуры данных количество задач для решения задач может не превышать как Big O(1) так и Big O log(n), в случае же выбора неподходящего типа структуры данных, то количество операций для решений той или иной задачи может быть в лучшем случае Big O(n), а в худшем Big O(n!)

Структуры данных и типы задач: 

| Структуры данных | Операция "Выборка" | Операция "Поиск" | Операция "Вставка" | Операция "Удаление" | 
| :--------------: | :----------------: | :--------------: | :----------------: | :-----------------: |
| Массив | 0(1) | 0(n) |  0(n) |  0(n) |
| Стэк | 0(n) | 0(n) | 0(1) | 0(1) |
| Очередь | 0(n) | 0(n) | 0(1) | 0(1) |
| Одинарный связной список | 0(n) | 0(n) | 0(1) | 0(1) |
| Двойной связной список | 0(n) | 0(n) | 0(1) | 0(1) |
| Хэш таблица | Нереализуемо | 0(1) | 0(1) | 0(1) |
| Бинарное поисковое дерево | 0(log(n)) | 0(log(n)) | 0(log(n)) | 0(log(n)) |
| В-Дерево | 0(log(n)) | 0(log(n)) | 0(log(n)) | 0(log(n)) |
| Красно-черное дерево | 0(log(n)) | 0(log(n)) | 0(log(n)) | 0(log(n)) |


## Простой связной список:
Особенность данной структуры данных в том, что каждый элемент списка состоит из самого элемента и ссылки на следующий элемент. Ключами же связного списка есть head и tail – маркеры первого и последнего элемента связного списка. <br/>
Для создания простого связного списка необходимо создать два класса - элемента узла списка (Node) и сам связной список (Linked list). <br/> <br/>

### Методы 
 Основными методами для управления связным списком являются: <br/>
- добавление(push) и удаление(pop) элементов из конца связного списка. <br/>
- добавление(unshift) и удаление(shift) элементов из начала связного списка. <br/>
- получение(get), перезапись(set) и удаление(remove) существующих элементов.  <br/>
- внедрение(insert) нового элемента в средину связного списка. <br/>
- реверсирование(reverse) всего связного списка. <br/> <br/>

#### Push
Push добавляет элемент вконец связного списка. <br/> <br/>
Реализация: <br/>
Создать два ключа, один из которых (head) отвечает за начало списка, другой (tail)  за конец списка. <br/> Новый элемент, который добавляется – присваивается переменной отвечающий за конец списка (tail). <br/> Отдельно инкрементировать длину связного списка. <br/> <br/>
Big 0(1): <br/>
Поскольку структурой данных обозначено как начало связного списка так и его конец, то для добавления элемента вконец списка необходимо лишь связать новый элемент с ключом tail и одновременно с этим передвинуть ключ tail на новый, последний, элемент связного списка.

#### Pop
Pop удаляет с конца элемент связного списка. <br/> <br/>
Реализация:  <br/>
Создать два ключа, которые ссылаются – один на последний элемент в связном списке, другой – на предидущий элемент в связном списке. <br/> После чего описываются разные варианты: когда нет ни единого элемента в связном списке, когда один элемент и когда два и больше элемента. <br/> <br/>
Big O(1): <br/>
Поскольку алгоритмом обозначено как начало связного списка так и конец, то для удаления элемента с конца необходимо лишь присвоить ссылку предпоследнего элемента Null. <br/> Последний элемент, является объектом, который был уже инициализирован и записан в памяти, в момент же, когда все ссылки на этот объект удаляются, то сборщик мусора JavaScript удаляет этот самый объект. <br/> Как итог результат достигается за одну операцию. <br/> <br/>  

#### Unshift
Unshift добавляет элемент в начало связного списка. <br/> <br/>
Реализация: <br/>
Создать два ключа, который первый отвечает за начало связного списка, а второй за конец. <br/> После чего при создании нового узла определить следующий элемент по списку – первым в связном листе. <br/> <br/>
Big O(1): <br/>
При добавлении в начало, происходит сдвиг на один элемент и одновременно с этим ссылка в новом элементе привязывается на бывший, первый элемент, это занимает одну операцию. <br/> <br/>

#### Shift 
Shift удаляет первый элемент связного списка. <br/> <br/>
Реализация: <br/> 
Создать два ключа, первый из которых отвечает за начало списка, а второй за конец списка. <br/> При использовании метода ключ отвечающий за начало – перемещается на следующий элемент и тем самым отвязывается от связующего списка (если на инициализированный и сохраненный в памяти объект нет ни одной ссылки, то сборщик мусора JavaScript удалит этот объект). <br/> <br/>
Big O(1): <br/>
При удалении первого элемента из списка, происходит удаление связи с одним элементом и одновременно с этим переписывание одной ссылки, это занимает одну операцию. <br/> <br/>

#### Get
Get получает элемент по его индексу. <br/> <br/>
Реализация: <br/>
В цикле пробежаться по элементам связного списка, где последняя итерация это  номер элемента в связном списке. <br/> Также необходимо учесть ситуацию, если желаемый индекс меньше нуля или больше длины всего связного списка. <br/> <br/>
Big O(n): <br/>
Перед тем, как получить элемент по заданному индексу необходимо пробежаться в цикле столько раз, сколько указано в самом индексе. <br/> <br/>

#### Set
Заменяет значение существующего  элемента связного списка на  новый. <br/> <br/>
Реализация: <br/>
В цикле пробежаться по элементам связного списка, где последняя итерация это номер элемента в связном списке, после чего значение этого элемента нужно заменить на новый, следовательно, для реализации метода Set должен принимать 2 аргумента: поисковый индекс и новое значение. <br/> Также необходимо учесть ситуацию, если желаемый индекс меньше нуля или больше длины всего связного списка. <br/> <br/>
Big O(n): <br/>
Перед тем, как получить элемент и его заменить по заданному индексу необходимо пробежаться в цикле столько раз, сколько указано в самом индексе. <br/> <br/>

#### Insert 
Добавляет один элемент в средину связного списка. <br/> <br/>
Реализация: <br/>
Использовать ранее созданный метод Get, чтобы получить индекс предыдущего элемента. После чего перезаписать ссылку этого элемента на тот, который добавляется методом Insert, после чего связующей ссылке у самого элемента вставленного с помощью метода Insert присвоить элемент, ранее присвоенный предыдущему элемента полученного с помощью Get. <br/> Также необходимо учесть следующие ситуации: 
- Если элемент вставляется по индексу первого элемента связного списка, то использовать метод Unshift. <br/>
- Если элемент вставляется по индексу последнего элемента связного списка, то использовать метод Push. <br/>
- Если индекс вставляемого элемента равняется меньше нуля или больше длины всего связного списка, то вернуть undefined. <br/> <br/>
Big O(n): <br/>
Посколько используется метод Get и после чего вставляется новый элемент, то метод Insert использует цикл, для того, чтобы пробежаться по тому количеству элементу, скольким равен сам индекс. <br/> <br/>



 


