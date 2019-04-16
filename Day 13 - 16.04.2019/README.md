## Читать

- C# 6.0 in a Nutshell. Joseph Albahari, Ben Albahari. O'Reilly Media. 2015.
Chapter 7. Collections
- C# in Depth. Jon Skeet. Manning Publications Co. 2013. Chapter 6. Implementing iterators the easy way.
- C# 5.0 Unleashed. Bart De Smet. Sams Publishing. 2013. Chapter 15. Generic Types and Methods. Chapter 16. Collection Types.
- Pro .NET Performance: Optimize Your C# Applications. Sasha Goldshtein. Chapter 5. Collections and Generics
- CLR via C#. Jeffrey Richter. Microsoft Press. 2010. Chapter 12. Generics.

## Задачи

1. (deadline - 21.04.2019) Разработать обобщенный класс-коллекцию BinarySearchTree (бинарное дерево поиска). Предусмотреть возможности использования подключаемого интерфейса для реализации отношения порядка. Реализовать три способа обхода дерева: прямой (preorder), поперечный (inorder), обратный (postorder): для реализации обходов использовать блок-итератор (yield). Протестировать разработанный класс, используя следующие типы:
  - System.Int32 (использовать сравнение по умолчанию и подключаемый компаратор);
  - System.String (использовать сравнение по умолчанию и подключаемый компаратор);
  - пользовательский класс Book, для объектов которого реализовано отношения порядка (использовать сравнение по умолчанию и подключаемый компаратор);
  - пользовательскую структуру Point, для объектов которого не реализовано отношения порядка (использовать подключаемый компаратор).
2. Продолжите таблицу
>
> Collection | Indexed lookup| Keyed lookup | Value lookup | Addition |  Removal |  Memory | 
>  -|-|-|-|-|-|-|
> T[] | | | | | | |
> List<T> | | | | | | |
> LinkedList<T> | | | | | | |
> Collection<T> | | | | | | |
> BindingList<T> | | | | | | |
> ObservableCollection<T>  | | | | | | |
> KeyCollection<TKey,TItem>  | | | | | | |
> ReadOnlyCollection<T>  | | | | | | |
> ReadOnlyObservableCollection<T>  | | | | | | |
>  | | | | | | |  
> Dictionary<TKey, TValue> | | | | | | |
>  | | | | | | |   
> SortedList<T> | O(1) |  O(log n) | O(n) | O(n)* | O(n) | Lesser| 
> SortedDictionary<TKey,TValue> | n/a | O(log n) | O(n) | O(log n) | O(log n) | Greater |  
> * `*`Вставка O(1) для уже упорядоченных данных.
>  
> Underlying structure | Lookup strategy | Ordering | Contiguous storage | Data access | Exposes Key & Value collection | 
>  -|-|-|-|-|-|
> 2 arrays | Binary search | Sorted | Yes | Key, Index | Yes |
> BST | Binary search | Sorted | No | Key | Yes | 




### [Репозиторий вопросов и ответов](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/.Net-Interview-Questions)

![](https://github.com/AnzhelikaKravchuk/Materials/blob/master/Pictures/Q%26A.png)
