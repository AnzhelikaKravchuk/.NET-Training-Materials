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

1. Даны два целых знаковых четырехбайтовых числа и две позиции битов i и j (i<=j). Реализовать алгоритм вставки первых (j - i + 1) битов второго числа в первое так, чтобы биты второго числа занимали позиции с бита i по бит j (биты нумеруются справа налево). Решение оформить  в виде статического метода InsertNumberIntoAnother статического класса NumbersExtension. Разработать модульные тесты (NUnit и MS Unit Test - ([DDT](https://msdn.microsoft.com/en-us/library/ms182527.aspx)))) для тестирования метода. (Ниже пояснение к алгоритму). **(deadline - 23.03.2019, 24.00)**. Примерные тест-кейсы

        [TestCase(2728, 655, 3, 8, ExpectedResult = 2680)]
        [TestCase(554216104, 15, 0, 31, ExpectedResult = 15)]
        [TestCase(-55465467, 345346, 0, 31, ExpectedResult = 345346)]
        [TestCase(554216104, 4460559, 11, 18, ExpectedResult = 554203816)]
        [TestCase(-1, 0, 31, 31, ExpectedResult = 2147483647)]
        [TestCase(-2147483648, 2147483647, 0, 30, ExpectedResult = -1)]
        [TestCase(-2223, 5440, 18, 23, ExpectedResult = -16517295)]
        [TestCase(2147481425, 5440, 18, 23, ExpectedResult = 2130966353)]
        NumbersExtension.InsertNumberIntoAnother(8, 15, 8, 3) => ArgumentException
        NumbersExtension.InsertNumberIntoAnother(8, 15, -1, 3) => ArgumentOutOfRangeException
        NumbersExtension.InsertNumberIntoAnother(8, 15, 32, 32) => ArgumentOutOfRangeException
        NumbersExtension.InsertNumberIntoAnother(8, 15, 0, 32) => ArgumentOutOfRangeException
        
![Схема к алгоритму](https://github.com/EPM-RD-NETLAB/.NET-Framework-modules/blob/master/Pictures/Scheme.png)
2. Реализовать *рекурсивный* алгоритм поиска максимального элемента в неотсортированном целочисленом массиве. Решение оформить  в виде статического метода FindMaxItem статического класса ArrayExtension.Разработать модульные тесты NUnit для тестирования метода. **(deadline - 22.03.2019, 24.00)**
3. Реализовать алгоритм поиска в целочисленном массиве индекса элемента, для которого сумма элементов слева и сумма элементов справа равны. Если такого элемента не существует вернуть null. Разработать модульные тесты NUnit. (**Padawans Task #11**) **(deadline - 23.03.2019, 24.00)**
4. Реализовать метод FilterArrayByKey который принимает массив целых чисел и фильтрует его таким образом, чтобы на выходе остались только числа, содержащие заданную цифру (LINQ-запросы не использовать!) Например, для цифры 7, метод FilterArrayByKey для набора {7,1,2,3,4,5,6,7,68,69,70,15,17} возвращает набор {7,7,70,17}. Разработать модульные тесты NUnit и MS Unit Test для тестирования метода. **(deadline - 24.03.2019, 18.00)**
