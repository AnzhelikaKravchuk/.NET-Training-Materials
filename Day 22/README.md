## Читать
- [C# 6.0 in a Nutshell. Joseph Albahari, Ben Albahari. O'Reilly Media. 2012.](http://shop.oreilly.com/product/0636920040323.do)
   - *Chapter 10.* LINQ to XML. [Samples](http://www.albahari.com/nutshell/ch10.aspx)
   - *Chapter 11.* Other XML Technologies. [Samples](http://www.albahari.com/nutshell/ch11.aspx)
   - *Chapter 17.* Serialization. [Samples](http://www.albahari.com/nutshell/ch15.aspx)

## Материалы (презентация)
- [XML Technologies](https://github.com/EPM-RD-NETLAB/.NET-Framework-modules/tree/master/M14.%20XML%20Technologies)
- [Serialization](https://github.com/EPM-RD-NETLAB/.NET-Framework-modules/tree/master/M15.%20Serialization)
- [Google Disk](https://drive.google.com/drive/u/0/folders/1VdIJ58NbH9Tx8ZqfWp3ZeSN9NsRoPVAc)

## Ключевые понятия
- Что такое XML 
- Что такое XSLT
- Что такое XPath
- Что такое XSD
- Что такое "well formed" XML документ
- Что такое "valid" XML документ?
- Способы валидации XML документа.
- .NET API интерфейсы для работы с  XML – данными.
- Механизмы сериализации.

## Задачи (deadline -)
  В текстовом файле построчно хранится информация об URL-адресах, представленных в виде
  
  ![Scheme](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/blob/master/Pictures/Scheme.png)

где сегмент parameters - это набор пар вида key=value, при этом сегменты URL‐path и parameters  или сегмент parameters могут отсутствовать. 
Разработать систему типов для экспорта данных, полученных на основе разбора информации текстового файла, в XML-документ по следующему правилу, например, для текстового файла с URL-адресами 
  - https://github.com/AnzhelikaKravchuk?tab=repositories 
  - https://github.com/AnzhelikaKravchuk/2017-2018.MMF.BSU
  - https://habrahabr.ru/company/it-grad/blog/341486/      

результирующим является XML-документ вида (можно использовать любую XML технологию без ограничений).

![XML-результат](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/blob/master/Pictures/XML.Task.png)

  Для тех URL-адресов, которые не совпадают с данным паттерном, “залогировать” информацию, отметив указанные строки, как необработанные. Для работы с URL можно использовать [Uri Class](https://msdn.microsoft.com/ru-ru/library/system.uri(v=vs.110).aspx).
  
  Продемонстрировать работу на примере консольного приложения.  

  Какие изменения нужно будет внести в систему типов, если в исходном  текстовом файле информация об URL-адресах изменится на другую, иерархически представимую информацию.

