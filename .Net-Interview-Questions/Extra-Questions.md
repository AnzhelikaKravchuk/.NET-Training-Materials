# Interview Questions

## C\#

### Разница между Value Туре и Reference Туре

Фундаментальное отличие между типами значений и ссылочными типами связанно с тем, каким образом они поддерживаются в памяти.

- Содержимое переменной или константы, относящейся к **типу значения**, является просто значение. Присваивание экземпляра типа значения всегда приводит к копированию этого экземпляра.
- содержимым переменной или константы **ссылочного типа** является ссылка на объект, который содержит значение. Присваивание переменной ссылочного типа вызывает копирование ссылки, но не экземпляра объекта.

### Что такое boxing/unboxing

### Как использовать ref, out и in

### Отличие "++х" от "х++"

### Разница между do...while и while

### Как работает delegate

### Как подписываться на события

### Разница между interface и abstract class

### Разница между protected и internal fields

### Что такое switch и case

### Создание custom attributes

### Создание generic types

### Что такое generic constraints

### Разница между extension и generic method

### Разница между anonymous delegate и lambda

### Как работает event

### Для чего нужен GetHashCode

### Разница между "==" и ReferenceEquals

```C#
public static bool ReferenceEquals (object objA, object objB);
```

Является статическим методом типа `System.Object`. Метод ReferenceEquals сравнивает две ссылки. Если ссылки на объекты идентичны, то возвращает true. Это значит, что данный метод проверяет экземпляры не на равенство, а на **тождество**.

В случае передачи этому методу экземпляров значимого типа (даже если передать один и тот же экземпляр) всегда будет возвращать false. Так произойдёт потому, что при передаче произойдёт упаковка значимых типов и ссылки на них будут разные.

В случае сравнения двух одинаковых (по значению) строк может выводить разные результаты. Это связанно с механизмом интернирования строк в .NET.

```C#
public static bool operator == (Foo left, Foo right)
```

Операторы == (равенство) и != (неравенство) проверяют равенство или неравенство своих операндов. Оператор равенства == возвращает значение true, если его операнды равны. В противном случае возвращается значение false.

- При сравнении **ссылочных типов** (Reference types), по умолчанию`*` ведет себя, как ReferenceEquals.
- Два операнда **string** равны, если они оба имеют значение null или оба экземпляра строки имеют одинаковую длину и идентичные символы в каждой позиции символа.
- Операнды **встроенных типов значений** равны, если равны их значения`**`.
- Два операнда одного типа **enum** равны, если равны соответствующие значения базового целочисленного типа.
- По умолчанию **пользовательские типы struct** не поддерживают оператор ==. Чтобы поддерживать оператор ==, пользовательская структура должна перегружать его.
- Начиная с версии C# 7.3 операторы == и != поддерживаются **кортежами** C#.

`*` - Определяемый пользователем тип может перегружать операторы == и !=. Если тип перегружает один из двух операторов, он должен также перегружать и другой.

`**` - Если любой из операндов не является числом (`Double.NaN` или `Single.NaN`), результат операции имеет значение false.

### Разница между Object.Equals(Object, Object) и Object.Equals(Object)

- Первый является **статическим** методом типа `System.Object`. Позволяет сравнивать объекты, если один или оба операнды равны - `null`. Сначала этот метод проверяет экземпляры на тождество и если объекты не тождественны, то проверяет их на null и делегирует ответственность за компарацию переопределяемому экземплярному методу Equals.

```C#
public static bool Equals(object objA, object objB)
{
   return objA == objB || (objA != null && objB != null && objA.Equals(objB));
}
```

- Второй является **экземплярным виртуальным** методом типа `System.Object`. По умолчанию, этот метод ведёт себя точно также как ReferenceEquals. Однако для значимых типов он переопределён в `System.ValueType`.

```C#
public virtual bool Equals(object obj)
{
    return RuntimeHelpers.Equals(this, obj);
}
```

### Разница между sealed и static class

### Как создавать anonymous delegate

### Разница между Func Action

- Делагат `Func` **возвращает результат действия** и может принимать параметры. Он имеет различные формы:

```C#
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T,out TResult>(T arg);
...
public delegate TResult Func<in T1,in T2,in T3,in T4,in T5,in T6,in T7,in T8,in T9,in T10,in T11,in T12,in T13,in T14,in T15,in T16,out TResult>(T1 arg1, T2 arg2, T3 arg3, T4 arg4, T5 arg5, T6 arg6, T7 arg7, T8 arg8, T9 arg9, T10 arg10, T11 arg11, T12 arg12, T13 arg13, T14 arg14, T15 arg15, T16 arg16);
```

- Делагат `Action` принимает параметры и **возвращает значение void**: Он имеет различные формы:

```C#
public delegate void Action();
public delegate void Action<in T>(T obj);
...
public delegate void Action<in T1,in T2,in T3,in T4,in T5,in T6,in T7,in T8,in T9,in T10,in T11,in T12,in T13,in T14,in T15,in T16>(T1 arg1, T2 arg2, T3 arg3, T4 arg4, T5 arg5, T6 arg6, T7 arg7, T8 arg8, T9 arg9, T10 arg10, T11 arg11, T12 arg12, T13 arg13, T14 arg14, T15 arg15, T16 arg16);
```

### Разница между Func и Predicate

Делегат `Predicate` как правило, используется для сравнения, сопоставления некоторого объекта T определенному условию. В качестве выходного результата возвращается значение true, если условие соблюдено, и false, если не соблюдено. Имеет только одну форму.

```C#
public delegate bool Predicate<in T>(T obj);
```

### Как реализован System.String

### Как использовать try...catch

### Создание nullable int

### Зачем использовать StringBuilder

### Создание enum types

### Разница между const и readonly fields

### Разница между static и const fields

### Как использовать Tuple

### Для чего нужен finally

### Когда использовать IDispose

### Реализация Dispose Pattern

### Как работает using совместно с IDispose

### Разница между "??", "?:" и "?."

?? - оператор объединения с NULL (null-coalescing operator). Он возвращает левый операнд, если этот операнд не имеет значение NULL; в противном случае возвращается правый операнд.

```C#
var beverage = GetBeerFromFridge() ?? GetBeerFromStore();
```

?: - условный оператор, известный как тернарный условный оператор (ternary conditional operator), вычисляет логическое выражение и возвращает результат вычисления одного из двух выражений, в зависимости от того, чему равно значение логического выражения: true или false.

```C#
int amount = today == Day.Friday || today == Day.Saturday ? 5 : 1;
```

?. and ?[] - null-условный оператор (null-conditional operators, Elvis operator) - если выражение в левой части оценивается как null - возвращает null (а не бросает NullReferenceException). Если его левая часть не null, присходит операция доступа к члену.

```C#
var lastOrder = customer?.Orders.?Last();
```

### Разница между this.Method() и base.Method()

### Что вернет typeof(int)

Возвращает объект `System.Type` представляющий тип `int`.

### Что вернет nameof(obj.Property).GetType()

1. `nameof(obj.Property)` возвращает строку со значением `"Property"`.
2. `"Property".GetType()` возвращает объект `System.Type` представляющий тип `string`.

### Отличие throw new от throw

## Collections

### Разница между O(1), O(log n) и O(n)

### Разница между Т[] и List\<T>

### Разница между ArrayList и List\<T>

### Разница между IEnumerable\<T> и IList\<T>

### Разница между ICollection и IList\<T>

### Разница между IReadOnlyCollection\<T> и IReadOnlyList\<T>

### Разница между List\<T> и Dictionary\<TKey, TValue>

### Разница между List\<T> и HashSet\<T>

### Разница между List\<T> и SortedDictionary\<TKey, TValue>

### Как использовать yield

### Разница между IEnumerable\<T> и IEnumerator

### Как работает binary tree

## GC

### Что такое GC и зачем нужны поколения

### Количество поколений

### Что делает GC.Collect

### Что делает GC.SuppressFinalize

### Разница между SOH и LOH

### Где размещаются struct и class в памяти

### Разница между f-reachable queue и finalization queue

## OOP

### Что нужно инкапсулировать

### Как реализовать полиморфное поведение в C\#

### Как использовать абстракцию

### Как наследовать классы в C\#

## .NET

### Что такое Assembly

### Что такое CLR

### Что такое AppDomain

### Что такое GAC

### Что такое IL

### Как работать с AppDomain

### Как работать с GAC

### Как работать с XmlSerializer (или JsonSerializer)

## LINQ

### Разница между First, FirstOrDefault, Single и SingleOrDefault

### Разница между All, Any и Contains

### Разница между Select и Where

### Использование GroupBy и GroupJoin

### Разница между Distinct и OrderBy

### Разница между Select и SelectMany

### Deferred execution

## SQL и RDBMS

### Как делать простые запросы SELECT, INSERT, UPDATE, DELETE. Как работает INNER JOIN и CROSS JOIN; реализация связей 1-1, 1-n

### Уровни изолированности транзакций, создание триггеров и хранимых процедур

### Как работают LEFT/RIGHT/FULL OUTER JOIN; основные агрегатные функции; как работают кластерные и некластерные индексы, как создавать индексы; реализация связи n-n

## ADO.NET

### Как создавать SqlClient, работать с connection string в App.config; создавать запрос на получение и изменение данных в БД с помощью DbCommand

### Как вызывать хранимые процедуры, получать данные через DataReader

## Entity Framework

### Db/Code/Model First

### Как делать Code First сущности и устанавливать связь 1-1 и 1-n

### Как описывать ключи и связи через атрибуты; что такое DbSet и DbContext

### Создание миграций

### Реализация отношений n-n

### Что такое lazy, eager и explicit loading и умею это использовать

### Как описывать связи в OnModelCreating

## Многопоточность

### Как использовать lock и Monitor

### Работа с потоками

### Использовние примитивов синхронизации ОС (mutex, semaphore, manual/auto reset event)

### Для чего нужен ThreadPool

### Разница между Task.WaitAll, Task.WaitAny, Task.WhenAll и Task.WhenAny

## Асинхронность

### Когда нужно использовать async

### Как работает await

### Зачем нужен ConfigureAwait

### «Подводные камни» await

### АРМ
