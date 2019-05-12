# Skills checklist

## C\#

### Знаю разницу между Value Туре и Reference Туре

В переменной типа значения храниться само значение, а в переменной ссылочного типа хранится адрес на объект в куче.

### Знаю, что такое boxing/unboxing

### Умею использовать ref и out

### Знаю разницу между "++х" и "х++"

### Знаю разницу межу do...while и while

### Знаю, как работает delegate

### Умею подписываться на события

### Знаю разницу межу interface и abstract class

### Знаю разницу межу protected и internal fields

### Знаю разницу между switch и case

### Умею создавать custom attributes

### Умею создавать generic types

### Знаю, что такое generic constraints

### Знаю разницу между extension и generic method

### Знаю разницу между anonymous delegate и lambda

### Знаю, как работает event

### Знаю, для чего нужен GetHashCode

### Знаю разницу между "==" и ReferenceEquals

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

### Знаю разницу между Object.Equals(Object, Object) и Object.Equals(Object)

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

### Знаю разницу между sealed и static class

### Умею создавать anonymous delegate

### Знаю разницу между Func Action

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

### Знаю разницу между Func и Predicate

Делегат `Predicate` как правило, используется для сравнения, сопоставления некоторого объекта T определенному условию. В качестве выходного результата возвращается значение true, если условие соблюдено, и false, если не соблюдено. Имеет только одну форму.

```C#
public delegate bool Predicate<in T>(T obj);
```

### Знаю, как реализован System.String

### Знаю, как использовать try...catch

### Умею создать nullable int

### Знаю, зачем использовать StringBuilder

### Умею создавать enum types

### Знаю разницу между const и readonly fields

### Знаю разницу между static и const fields

### Умею использовать Tuple

### Знаю, для чего нужен finally

### Знаю, когда использовать IDispose

### Умею реализовать Dispose Pattern

### Знаю, как работает using совместно с IDispose

### Знаю разницу между "??", "?:" и "?."

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

### Знаю разницу между this.Method() и base.Method()

### Знаю, что вернет typeof(int)

Возвращает объект `System.Type` представляющий тип `int`.

### Знаю, что вернет nameof(obj.Property).GetType()

1. `nameof(obj.Property)` возвращает строку со значением `"Property"`.
2. `"Property".GetType()` возвращает объект `System.Type` представляющий тип `string`.

### Знаю разницу между throw new и throw

## Collections

### Знаю разницу между O(1), O(log n) и O(n)

### Знаю разницу между Т[] и List\<T>

### Знаю разницу между ArrayList и List\<T>

### Знаю разницу между IEnumerable\<T> и IList\<T>

### Знаю разницу между ICollection и IList\<T>

### Знаю разницу между IReadOnlyCollection\<T> и IReadOnlyList\<T>

### Знаю разницу между List\<T> и Dictionary\<TKey, TValue>

### Знаю разницу между List\<T> и HashSet\<T>

### Знаю разницу между List\<T> и SortedDictionary\<TKey, TValue>

### Умею использовать yield

### Знаю разницу между IEnumerable\<T> и IEnumerator

### Знаю, как работает binary tree

## GC

### Знаю, что такое GC и зачем нужны поколения

### Знаю количество поколений

### Знаю, что делает GC.Collect

### Знаю, что делает GC.SuppressFinalize

### Знаю разницу между SOH и LOH

### Знаю, где размещаются struct и class в памяти

### Знаю разницу между f-reachable queue и finalization queue

## OOP

### Знаю, что нужно инкапсулировать

### Умею реализовать полиморфное поведение в C\#

### Умею использовать абстракцию

### Умею наследовать классы в C\#

## .NET

### Знаю, что такое Assembly

### Знаю, что такое CLR

### Знаю, что такое AppDomain

### Знаю, что такое GAC

### Знаю, что такое IL

### Умею работать с AppDomain

### Умею работать с GAC

### Умею работать с XmlSerializer (или JsonSerializer)

## LINQ

### Знаю разницу между First, FirstOrDefault, Single и SingleOrDefault

### Знаю разницу между All, Any и Contains

### Знаю разницу между Select и Where

### Умею использовать GroupBy и GroupJoin

### Знаю разницу между Distinct и OrderBy

### Знаю разницу между Select и SelectMany

### Знаю, что такое deferred execution

## SQL и RDBMS

### Умею делать простые запросы SELECT, INSERT, UPDATE, DELETE. Знаю, как работает INNER JOIN и CROSS JOIN; знаю как реализовать связь 1-1, 1-n.

### Знаю уровни изолированности транзакций, умею создавать триггеры и хранимые процедуры

### Знаю, как работают LEFT/RIGHT/FULL OUTER JOIN; знаю основные агрегатные функции; понимаю, как работают кластерные и некластерные индексы, умею создавать индексы; знаю как реализовать связь n-n

## ADO.NET

### Умею создавать SqlClient, работать с connection string в App.config; создавать запрос на получение и изменение данных в БД с помощью DbCommand

### Умею вызыватьхранимые процедуры, получать данные через DataReader

## Entity Framework

### Знаю, что такое Db/Code/Model First

### Умею делать Code First сущности и устанавливать связь 1-1 и 1-n

### Умею описывать ключи и связи через атрибуты; знаю что такое DbSet и DbContext

### Умею создавать миграции

### Умею реализовывать отношение n-n;

### Знаю, что такое lazy, eager и explicit loading и умею это использовать

### Умею описывать связи в OnModelCreating

## Многопоточность

### Умею использовать lock и Monitor

### Умею работать с потоками

### Знаю и умею использовать примитивы синхронизации ОС (mutex, semaphore, manual/auto reset event)

### Знаю, для чего нужен ThreadPool

### Знаю разницу между Task.WaitAll, Task.WaitAny, Task.WhenAll и Task.WhenAny

## Асинхронность

### Понимаю, когда нужно использовать async

### Понимаю, как работает await

### Знаю, зачем нужен ConfigureAwait

### Знаю «подводные камни» await

### Знаю и умею АРМ
