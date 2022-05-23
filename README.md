# Структуры данных и алгоритмы

## Оглавление

- [Cтруктуры данных и алгоритмы](#структуры-данных-и-алгоритмы)
  - [Оглавление](#оглавление)
  - [Big O](#big-o)
  - [Простой связной список](#Простой-связной-список)
  - [Двойной связной список](#Двойной-связной-список)
  - [Стэк](#Стэк)
  - [Очередь](#Очередь)
  - [Бинарное поисковое дерево](#Бинарное-поисковое-дерево)
  - [Хэш-таблица](#Хэш-таблица)
  - [Граф](#Граф)

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


## Простой связной список
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

#### Remove
Удаляет один элемент из связного списка. <br/> <br/>
Реализация: <br/>
Использовать ранее созданный метод Get, чтобы получить индекс предыдущего элемента, после чего перезаписать ссылку этого элемента на сторонний ключ, к примеру before, а связывающую ссылку у before связать с элементом идущим через одного. Тем самым у указанного элемента по индексу отсутствуют ссылки на другие объекты, и на этот объект больше нет ни одной ссылки, поэтому этот, заданный по индекс, будет удалён сборщиком мусора JavaScript. <br/> Также необходимо учесть следующие ситуации: 
- Если элемент удаляется по индексу первого элемента связного списка, то использовать метод Shift. <br/>
- Если элемент удаляется по индексу последнего элемента связного списка, то использовать метод Pop. <br/>
- Если индекс удаляемого элемента равняется меньше нуля или больше длины всего связного списка, то вернуть undefined. <br/>

Big O(n): <br/>
Поскольку используется метод Get и после чего перепривязываеться существующий элемент, то метод Remove использует цикл, для того, чтобы пробежаться по тому количеству элементу, скольким равен сам индекс. <br/> <br/>

#### Reverse 
Реверсирует весь связной список. <br/> <br/>
Реализация: <br/>
У связного списка есть два основополагающий ключа один из которых обозначает начало связного списку (head), а другой – конец связного списка (tail), которым присваиваются противоположные элементы, после чего все элементы перезаписывают ссылки в обратную сторону. <br/> <br/>

Big O(n): <br/>
Метод использует цикл, который равняется длине всего связного списка. <br/> <br/>

## Двойной связной список

Особенность данной структуры данных в том, что каждый элемент списка состоит из самого элемента,  ссылки на следующий и предыдущий  элементы. Ключами же связного списка помимо есть: <br/>
- head и tail, маркеров который обозначают первый и последний элемент связного списка. <br/>
- next и prev – ключи, которые являются ссылками на предидущий и следующий элемент связного списка. <br/>
Для создания простого связного списка необходимо создать два класса - элемента узла списка (Node) и сам двойной связной список (Double linked list). <br/> <br/>

### Методы: <br/>
Основными методами двойного связного списка есть: <br/>
- добавление(push) и удаление(pop) элементов из конца связного списка. <br/>
- добавление(unshift) и удаление(shift) элементов из начала связного списка. <br/>
- получение(get), перезапись(set) и удаление(remove) существующих элементов. <br/>
- внедрение(insert) нового элемента в средину связного списка. <br/>

#### Push

Push добавляет элемент вконец двойного связного списка. <br/> <br/>
Реализация: <br/>
Создать два ключа, один из которых (head) отвечает за начало списка, другой (tail) за конец списка. Новый элемент, который добавляется – присваивается переменной отвечающий за конец списка (tail). <br/> При добавлении элемента заместо Null присваивается новый элемент списка, при этом tail имеет ссылку как на предидущий элемент (pred) и на следующий элемент (next) который является Null. <br/> Отдельно инкрементируется длину двойного связного списка. <br/> <br/>
Big 0(1): <br/>
Поскольку структурой данных обозначено как начало связного списка так и его конец, то для добавления элемента вконец списка необходимо лишь связать новый элемент с ключом tail и одновременно с этим передвинуть ключ tail на новый, последний, элемент связного списка. <br/> <br/>

#### Pop

Pop удаляет с конца элемент связного списка. <br/> <br/>
Реализация: <br/>
Создать два ключа, которые ссылаются – один на последний элемент в двойном связном списке, другой – на предидущий элемент в связном списке. Перенести tail на предидущий элемент, ссылку на следующий элемент (next) у этого, предидущего элемента присвоить Null. <br/> <br/>
Big O(1): <br/>
Поскольку алгоритмом обозначено как начало двойного связного списка так и конец, то для удаления элемента с конца необходимо лишь присвоить ссылку предпоследнего элемента Null. Последний элемент, является объектом, который был уже инициализирован и записан в памяти, в момент же, когда все ссылки на этот объект удаляются, то сборщик мусора JavaScript удаляет этот самый объект. <br/> Как итог результат достигается за одну операцию. <br/> <br/>

#### Unshift

Unshift добавляет элемент в начало связного списка. <br/> <br/>
Реализация: <br/>
Создать два ключа, который первый отвечает за начало связного списка, а второй за конец. <br/>
После чего при создании нового узла определить следующий элемент по списку – вторым в связном листе. <br/> <br/>

Big O(1): <br/>
При добавлении в начало, происходит сдвиг на один элемент и одновременно с этим ссылка на следующий элемент (next) в новом элементе привязывается на первый  элемент и одновременно с этим ссылке на предидущий элемент (prev) присваивается Null, это занимает одну операцию. <br/> <br/>

#### Shift

Shift удаляет первый элемент связного списка. <br/> <br/>
Реализация: <br/>
Создать два ключа, первый из которых отвечает за начало списка, а второй за конец списка. <br/>
При использовании метода ключ отвечающий за начало – перемещается на следующий элемент и тем самым отвязывается от связующего списка (если на инициализированный и сохраненный в памяти объект нет ни одной ссылки, то сборщик мусора JavaScript удалит этот объект). <br/> <br/>
Big O(1): <br/>
При удалении первого элемента из списка, происходит удаление связи с одним элементом и одновременно с этим переписывание одной ссылки, это занимает одну операцию. <br/> <br/>

#### Get

Get получает элемент по его индексу. <br/> <br/>
Реализация: <br/>
В цикле пробежаться по элементам двойного связного списка, где последняя итерация это номер элемента в связном списке. <br/>
Также необходимо учесть ситуацию, если желаемый индекс меньше нуля или больше длины всего связного списка. <br/> <br/>
Big O(n): <br/>
Перед тем, как получить элемент по заданному индексу в двойном связном списке необходимо пробежаться в цикле столько раз, сколько указано в самом индексе. <br/> <br/>

#### Set

Заменяет значение существующего элемента связного списка на новый. <br/> <br/>
Реализация: <br/>
В цикле пробежаться по элементам двойного связного списка, где последняя итерация это номер элемента в связном списке, после чего значение этого элемента нужно заменить на новый, следовательно, для реализации метода Set должен принимать 2 аргумента: поисковый индекс и новое значение. <br/>
Также необходимо учесть ситуацию, если желаемый индекс меньше нуля или больше длины всего связного списка. <br/> <br/>
Big O(n): <br/>
Перед тем, как получить элемент и его заменить по заданному индексу необходимо пробежаться в цикле столько раз, сколько указано в самом индексе. <br/> <br/>

#### Insert

Добавляет один элемент в средину связного списка. <br/> <br/>
Реализация: <br/>
Использовать ранее созданный метод Get, чтобы получить индекс предыдущего элемента. После чего перезаписать ссылку этого элемента на тот, который добавляется методом Insert, после чего связующей ссылке у самого элемента вставленного с помощью метода Insert присвоить элемент, ранее присвоенный предыдущему элемента полученного с помощью Get с помощью ключей prev, а следующий с помощью next. <br/> <br/>
Также необходимо учесть следующие ситуации: <br/>
- Если элемент вставляется по индексу первого элемента связного списка, то использовать метод Unshift. <br/>
- Если элемент вставляется по индексу последнего элемента связного списка, то использовать метод Push. <br/>
- Если индекс вставляемого элемента равняется меньше нуля или больше длины всего связного списка, то вернуть undefined. <br/> <br/>

Big O(n): <br/>
Посколько используется метод Get и после чего вставляется новый элемент, то метод Insert использует цикл, для того, чтобы пробежаться по тому количеству элементу, скольким равен сам индекс. <br/> <br/>

#### Remove 

Удаляет один элемент из связного списка. <br/> <br/>
Реализация: <br/>
Использовать ранее созданный метод Get, чтобы получить индекс предыдущего элемента, после чего перезаписать ссылку этого элемента на сторонний ключ, к примеру before, а связывающую ссылку у before связать с элементом идущим через одного. Тем самым у указанного элемента по индексу отсутствуют ссылки на другие объекты, и на этот объект больше нет ни одной ссылки, поэтому этот, заданный по индекс, будет удалён сборщиком мусора JavaScript. <br/> <br/>
Также необходимо учесть следующие ситуации: <br/>
- Если элемент удаляется по индексу первого элемента связного списка, то использовать метод Shift. <br/>
- Если элемент удаляется по индексу последнего элемента связного списка, то использовать метод Pop. <br/>
- Если индекс удаляемого элемента равняется меньше нуля или больше длины всего связного списка, то вернуть undefined. <br/> <br/>

Big O(n): <br/>
Посколько используется метод Get и после чего перепривязывается существующий элемент, то метод Remove использует цикл, для того, чтобы пробежаться по тому количеству элементу, скольким равен сам индекс. <br/> <br/>

## Стэк

Особенность данной структуры данных является то, что элементы двигаются по системе FILO – first input last output (первый зашел последний вышел). <br/> Примерами из реальности служат разгруженные на полках магазинов стопки продуктов, будь-то пакеты с соком или бутылки с молоком. <br/> Примерами же из сферы программирования есть возможность откатывать историю действий назад, как например история в браузере. <br/>
Стэк образовывается за счёт двух классов: первый класс это сам элемент стэка, а второй класс сам стэк, который реализовывает методы по управлению элементами. <br/> <br/>

### Методы

Методами стэка являются: <br/>
- добавление и удаление элементов в стэке. <br/>
- проверка на пустоту стэка. <br/>
- получение значения верхнего элемента в стэке. <br/>

#### Push

Добавляет элемент в стэк. <br/> <br/>

Реализация: <br/>
Поскольку стэк наполняется и опустошается сверху, то для пометки верхнего элемента в стэке необходимо создать ключ – top, он будет означать первый элемент в стэке. При добавлении нового элемента в стэк нужно передвигать ключ top на новый элемент. <br/>
Также каждый элемент вставляемый в стэк должен иметь как само значение так и ссылку на нижний элемент. При добавлении нового элемента, автоматически присваивается ссылке нижний, предидущий элемент. <br/> <br/>

Big O(1): <br/>
Поскольку работа всегда ведется с верхним элементом, который сдвигается вниз и одновременно с этим вставляется новый элемент, то выполняется лишь 1 операция. <br/> <br/>

#### Remove

Удаляет первый элемент из стэка. <br/> <br/>

Реализация: <br/>
Поскольку стэк наполняется и опустошается сверху, то для пометки верхнего элемент в стэке необходимо создать ключ – top, он будет означать первый элемент в стэке. <br/>
При вызове метода Remove необходимо переопределить ключ top, на следующий элемент в стэке, а верхний элемент отвязать от стэке – присвоив ссылке в верхнем элементе  - Null. <br/>
При отсутствии ссылок на инициализированный и сохраненный в памяти объект сборщик мусора JavaScript удаляет этот объект из памяти без участия программиста. <br/>

Big O(1): <br/>
Поскольку работа всегда ведется с верхним элементом, который  удаляется и одновременно с этим второй элемент становится первым, то выполняется лишь 1 операция. <br/>

#### isEmpty

Проверяет пустой ли стэк <br/> <br/>

Реализация: <br/>
К методам удаления и наполнения стэка добавить инкремент и декремент. С исполнением методов push и remove увеличивается или уменьшается длина стэка. Эта длина если больше 1, то метод возвращает false, если пустой – true. <br/>

Big O(1): <br/>
Возвращает или true или false в зависимости от длины стэка, это 1 операция. <br/>

#### Peek

Получить первый элемент стэка <br/>

Реализация: <br/>
Поскольку стэк имеет ключ top, который всегда привязан к первому элементу в стэкэ, то и суть метода заключается в том, чтобы возвращать значение, на которое ссылается top. <br/> <br/>

Big O(1): <br/>
Возвращает значение, на который указывает ключ top, это 1 операция. <br/> <br/>

## Очередь

Особенность данной структуры является то, что элементы двигаются по системе FIFO – first input first out (первый зашел, первый вышел). <br/> Примерами из реальности служат, как не странно, любые очереди в магазины, банки или подобное. <br/> Примерами же из сферы программирования есть возможность листать ленту в Instagram или TikTok. <br/>
Очередь реализовывается с помощью двух классов: класс элемента и класс очереди, которая реализовывает элементы в зависимости от метода класса. <br/> <br/>

### Методы
Методами очереди являются: <br/>
- добавление и удаление элементов из очереди. <br/>
- проверка очереди на пустоту. <br/>
- получение первого и последнего элемента очереди. <br/> <br/>

#### Enqueue

Добавляет элемент в очередь. <br/>

Реализация: <br/>
Очередь состоит из ключей first и last, которые определяют начало и конец очереди. Метод определяет два варианта: <br/>
1.	Если очередь пуста, то ключи first и last ссылаются на один элемент. <br/>
2.	Если очередь имеет один или больше элементов, то ключ first ссылается на новый элемент, а last на прошлый. <br/> <br/>

Big O(1): <br/>
Поскольку каждый элемент имеет ссылку на предидущий элемент, то у последнего элемента в очереди ссылка ссылается на Null. Внедрение записи о новом элементе в очереди это одна операция. <br/> <br/>

#### Dequeue

Удаляет элемент из очереди. <br/> <br/>

Реализация: <br/>
Поскольку первый элемент в очереди всегда привязан к ключу first, то и удалить его это по сути перезаписать ключ first на второй элемент очереди, а связную ссылку у первого элемента присвоить Null. <br/>
Объект, который был инициализирован и записан в память не имеющий никаких связей автоматически стирается сборщиком мусора JavaScript. <br/>
Также отдельно в методе необходимо учесть условие, если очередь пуста, следовательно метод должен возвращать undefined. <br/> <br/>

Big O(1): <br/>
Поскольку ключ first всегда привязан к первому элементу очереди, поэтому удалить его не составит труда. <br/> <br/>

#### isEmpty

Проверяет пустая ли очередь <br/> <br/>

Реализация: <br/>
К методам удаления и наполнения очереди добавить инкремент и декремент. С исполнением методов enqueue  и dequeue  увеличивается или уменьшается длина очереди. Эта длина если больше 1, то метод возвращает false, если пустой – true. <br/> <br/>

Big O(1): <br/>
Возвращает или true или false в зависимости от длины очереди, это 1 операция. <br/> <br/>

#### first

Получить первый элемент очереди. <br/> <br/>

Реализация: <br/>
Поскольку очередь  имеет ключ first, который всегда привязан к первому элементу в очереди, то и суть метода заключается в том, чтобы возвращать значение, на которое ссылается first. <br/> <br/>

Big O(1): <br/>
Возвращает значение, на который указывает ключ first, это 1 операция. <br/> <br/>

#### last

Получить последний элемент очереди. <br/> <br/>

Реализация: <br/>
Поскольку очередь  имеет ключ last, который всегда привязан к последнему элементу в очереди, то и суть метода заключается в том, чтобы возвращать значение, на которое ссылается last. <br/> <br/>

Big O(1): <br/>
Возвращает значение, на который указывает ключ last, это 1 операция. <br/> <br/>

## Бинарное поисковое дерево

Особенностью данной структуры данных является принцип разделения на два вектора значений. Таким образом создаётся дерево с различными значениями, которые вкладываются в условие бинарного поиска. <br/>
Бинарный поиск отличается от линейного поиска тем, что в линейном поиске поиск происходит элемент за элементом и тем самым количество потенциальных операций линейного поиска равняется значению поискового элемента. <br/>
Бинарный поиск -  это поиск через условие: значение проверяется на равенство со следующим значением в дереве.  В зависимости от того, если значение больше или меньше поиск откидывает ровно половину всех значений. Таким образом поиск происходит всегда отделяя половину значений. <br/>
Для реализации класса бинарного поискового дерева необходимы 2 класса: первый класс это элемент бинарного дерева, который имеет два ключа ответвление в лево и право и ключ определяющий значение элемента. Вторым классом является само бинарное дерево, которое имеет методы управления элементами. <br/>

### Методы
Методы работы с бинарным деревом являются: <br/>
- Вставка значения в дерево. <br/>
- Проверка на наличие значения в дереве. <br/>
- Получение минимального значения в дереве. <br/> <br/>

#### Insert

Вставка значения в дерево. <br/> <br/>
Реализация: <br/>
При вставке любого из значений, это значение проходит условие на равенство с предидущим значением, которое есть в дереве. Если значение больше, чем существующее - оно уходит в левую ветку, если меньше существующего – уходит в право. <br/> <br/>
Big O(log n): <br/>
При вставке последующего элемента в дерево, его значение проходит условия и сравниваясь за каждую операцию откидывает половину дерева. Таким образом количество операций для достижения результата стоит как логарифм от количества операций. <br/> <br/>

#### Contains:

Проверка на наличие значений в дереве. <br/> <br/>
Реализация: <br/>
При прохождении по дереву, значение, которое принимается первым аргументом проверяется сперва на соответствие условию по ветке, после чего или находит данное значение в дереве и возвращает true или не находит и получает значение Null, что выведет значение false. <br/> <br/>
Big O(log n): <br/>
При поиске элемента в дереве, элемент проходит условие на равенство с предидущим значением, которое есть в дереве. Если значение больше, чем существующее - оно уходит в левую ветку, если меньше существующего – уходит в право. <br/>
Таким образом после каждой проверки откидывается половина значений дерева. <br/>
Результатом поиска элемента может быть как найденный элемент так и Null – поэтому в худшем случае для достижения результата, поиску придется пройти все уровни дерева. <br/> <br/>

#### MinimalValue

Поиск элемента с минимальным значением начиная с соответствующего уровня вложенности бинарного поискового дерева. <br/> <br/>
Реализация: <br/>
При прохождении по дереву проверяется начальное значение, которое определяется уровнем расположения элемента в дереве с элементом, который ответвлен с левой стороны плеча (поскольку по условию в левую сторону дерева отсылаются значения меньше номинального). <br/> <br/>
Big O((log n)/2): <br/>
При поиске минимального значения в дереве поиск всегда будет происходить по левому плечу, посколько исходя из описанного метода структуры данных, в левое плечо уходит значение меньше от сравнимого. <br/> <br/>

## Хэш-таблица

Хэширование это метод для преобразований значений ключа в индекс. Зная этот индекс, можно получить очень быстро значения, при этом не важна сложность этих значений. <br/>
Хеш-таблица это ассоциативный массив, который состоит из индекса, преобразованного из ключ с помощью хеширования и значения, которое этот индекс хранит. <br/>
Для создания хэш таблицы нужна приватная хэш функция, которая будет преобразовывать значение ключа в индекс и наоборот. <br/>
Отдельно стоит учесть вероятность коллизий. Коллизия - это полное совпадение индексов в хеш-таблице. При коллизиях здесь реализован метод – цепочка результатов. Таким образом один элемент хеш-таблицы изначально является массивом, в который вставляются массивы по типу: индекс/значение. Эти массивы перечисляются внутри одного, общего, массива через запятую. <br/> <br/>

### Методы
Методы для работы с хэш-таблицей: <br/>
- Получение (get) элемента хэш-таблицы. <br/>
- Запись (set) элементов в хеш таблицу. <br/>
-  Получение массива всех ключей хэш-таблицы. <br/> <br/>

#### Get

Получить элемент из хэш-таблицы зная его ключ. <br/> <br/>
Реализация: <br/>
Чтобы получить элемент из хэш-таблицы необходимо сперва узнать его индекс. Индекс вычисляется путём вставки ключа в работу хэш-функции. После чего пробежавшись циклом по количеству значений, которые попадают под этот индекс, можно получить все значения этого ключа. <br/> <br/>
Big O(1): <br/>
Поскольку зная ключ, можно получить сразу все значения массива по его индексу, то это одна операция. В случаем ж, если получения значения по его индексу в простом массиве это была ы сложность Big O(n), поскольку количество операций сравнения равняется размеру индекса указанного в поисковом запросе. <br/> <br/>

#### Set

Записать элемент в хэш таблицу. <br/> <br/>
Реализация: <br/>
Чтобы записать элемент в хеш-таблицу необходимо указать первым аргументом ключ, по которому можно будет достать значение и вторым аргументом само значение. Сперва нужно вычислять индекс элемент с помощью подстановки аргумента ключа в работу хеш-функции, после чего вставить элемент в соответствии с вычисляемым индексом. <br/> <br/>
Big O(1): <br/>
Результатом работы хэш-функции является массив пары индекс/значение, который вставляется в конкретную ячейку ассоциативного массива хеш-функции. Таким образом это одна операция. <br/> <br/>

#### Keys

Подучить все ключи хеш-таблицы. <br/> <br/>
Реализация: <br/>
Чтобы получить все ключи хеш-таблицы нужно пробежать циклом по всей длине этой хэш-таблицы, где длина этой хеш-таблицы равняется количеству элементов в этой таблице. <br/> <br/>
Big O(n): <br/>
Результатом вывода будет массив всех ключей, которые получаются как результат работы цикла с участием хэш-функции. Количество операций зависит от количества индексов, которые есть в хеш-таблице. <br/> <br/>

## Граф
Особенностью данной структуры данных являются цепные связи. Каждый элемент графа может быть взаимосвязанным с любым количеством других, аналогичных связей. Граф подобен взаимозависимости One-To-Many в базах данных. <br/>
Подобные зависимости встречаются в реализации функции друзей в Facebook или Instagram, когда у нас есть один элемент – профиль пользователя и связи с другими элементами – другие пользователями, которые являются его друзьями. <br/>
Также графы с вычисляемыми длинами связей используется в приложениях, которые формируют маршруты движений. <br/> <br/>
Структуру графа может быть представлена как смежная матрица зависимостей связей,  в которой каждый элемент определяет зависимости с другими элементами путём логического значения true. <br/>

Смежная матрица из 5 элементов: <br/>

| - | А | В | С | D | E |
| - | - | - | - | - | - |
| А | 0 | 1 | 0 | 0 | 1 |
| В | 1 | 0 | 1 | 0  | 0 |
| С | 0 | 1 | 0 | 1 | 0 |
| D | 0 | 0 | 1 | 0 | 1 |
| Е | 1 | 0 | 0 | 1 | 0 |

В рамках небольшого количества элементов матрица может быть и разумное решение, но если элементов с миллион, к примеру в социальной сети есть миллион пользователей и одного из этих пользователей лишь один друг (связь с другим элементом), то в смежной матрице у одного элемента будет лишь одна истина (1), а остальные 999 999 элементов будут заполнены ложью (0), что делает такую матрицу огромной и при этом не рационально используемой.  <br/>
Структуру графа может быть представлена также как и смежный список – объект, где каждый ключ - это название элемента, а значение ключа – массив, который состоит из связных элементов.  <br/>
Смежный список из 5 элементов:  <br/>
’’’nodejs
{
“A”: [“B”, “E”],
“B”: [“С”, “A”],
“C”: [“B”, “D”],
“D”: [“C”, “E”],
“E”: [“D”, “E”]
}
’’’

Отличие смежного листа от смежной матрицы в реализации связей. Количество элементов остаётся таким же, но фактически связи прописываются в массиве связей, поэтому отсутствие связей означает не наполнение элемента нулями, а отсутствием данных.  <br/>
Далее реализация пойдет смежного листа. <br/> <br/>

### Методы
Методы для использования графов: <br/>
- Добавление и удаление элементов. <br/>
- Добавление и удаление связей с определенными элементами. <br/>


## Алгоритмы

### Алгоритмы со строковыми значениями:

#### Анаграмы 

Анаграмы - это разные слова, которые могут быть написаны с помощью одних и тех же букв с учётом их количества и длины самого слова.

Примеры: 
- `rail safety` и `fairy tales` - True
- `` и `` - False 

Примеры решения с кодом: 