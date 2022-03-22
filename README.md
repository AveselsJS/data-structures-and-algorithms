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
Особенность данной структуры данных в том, что каждый элемент списка состоит из самого элемента и ссылки на следующий элемент. Ключами же связного списка есть head и tail – маркеры первого и последнего элемента связного списка. <br/> <br/>

### Методы: 
 Основными методами для управления связным списком являются: <br/>
- добавление и удаление  элементов из начало и конца связного списка.  <br/>
- получение, перезапись и удаление  существующих элементов.  <br/>
- реверсирование всего связного списка. <br/> <br/>
