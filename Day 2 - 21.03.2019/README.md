## Читать
- Ian Griffiths. Programming C# 5.0.  Chapter 2,  Numeric Types.
- Joseph Albahari, Ben Albahari C# 5.0 (6.0) in a Nutshell. Chapter 6. Framework Fundamentals - Working with Numbers
- The Art of Unit Testing. ROY OSHEROVE. PART 1 GETTING STARTED.
- [Что нужно знать про арифметику с плавающей запятой](https://habrahabr.ru/post/112953/)
- [Get started with unit testing](https://docs.microsoft.com/en-us/visualstudio/test/getting-started-with-unit-testing) или [Приступая к работе с модульным тестированием](https://docs.microsoft.com/ru-ru/visualstudio/test/getting-started-with-unit-testing)

## Дополнительные материалы
- [Basic Coding in C#](https://github.com/EPM-RD-NETLAB/.NET-Framework-modules/tree/master/M2.%20Basic%20Coding%20in%20C%23)
- [C# Unit Testing](https://github.com/EPM-RD-NETLAB/.NET-Framework-modules/tree/master/M5.%20C%23%20Unit%20Testing)

## Задачи
1. Даны два целых знаковых четырехбайтовых числа и две позиции битов i и j (i<=j). Реализовать алгоритм InsertNumber вставки первых (j - i + 1) битов второго числа в первое так, чтобы биты второго числа занимали позиции с бита i по бит j (биты нумеруются справа налево). Разработать модульные тесты (NUnit и MS Unit Test - ([DDT](https://msdn.microsoft.com/en-us/library/ms182527.aspx)))) для тестирования метода. (Ниже пояснение к алгоритму). **(deadline - 23.03.2019, 24.00)**
![Схема к алгоритму](https://github.com/EPM-RD-NETLAB/.NET-Framework-modules/blob/master/Pictures/Scheme.png)
2. Реализовать *рекурсивный* алгоритм поиска максимального элемента в неотсортированном целочисленом массиве. Разработать модульные тесты NUnit для тестирования метода. **(deadline - 22.03.2019, 24.00)**
3. Реализовать алгоритм поиска в вещественном массиве индекса элемента, для которого сумма элементов слева и сумма элементов справа равны. Если такого элемента не существует вернуть null. Разработать модульные тесты NUnit. (**Padawans Task #11**) **(deadline - 23.03.2019, 24.00)**
4. Реализовать метод FilterArrayByKey который принимает массив целых чисел и фильтрует его таким образом, чтобы на выходе остались только числа, содержащие заданную цифру (LINQ-запросы не использовать!) Например, для цифры 7, метод FilterArrayByKey для набора {7,1,2,3,4,5,6,7,68,69,70,15,17} возвращает набор {7,7,70,17}. Разработать модульные тесты NUnit и MS Unit Test для тестирования метода. **(deadline - 24.03.2019, 18.00)**
