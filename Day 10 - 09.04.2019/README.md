## Читать
- C# in Depth. Jon Skeet. Manning Publications Co. 2013. Chapter 14. Dynamic binding in a static language.

## Tasks

- Переобразовать методы расширения класса ArrayExtension [Day 7](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/Day%207%20-%2002.04.2019) в обобщенно-типизированные методы
      
      public static TSource[] Filter<TSource>(this TSource[] source, IPredicate<TSource> predicate) { }
      
      public static TResult[] Transform<TSource,TResult>(this TSource[] source, ITransformer<TSource, TResult> transformer) { }
      
      public static TSource[] SortBy<TSource>(this TSource[] source, IComparer<TSource> comparer) { } 
  
- Проверить работу полученных методов, используя в качестве тест-кейсов постановки задач из [Day 7](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/Day%207%20-%2002.04.2019)
- Набор целочисленных зачений представлен массивом строк, каждая из которых является представлением соответствующего целого числа в p-ичной (2<=p<=16) системе счисления. Получить набор целочисленных значений.

### [Репозиторий вопросов и ответов](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/.Net-Interview-Questions)

![](https://github.com/AnzhelikaKravchuk/Materials/blob/master/Pictures/Q%26A.png)
