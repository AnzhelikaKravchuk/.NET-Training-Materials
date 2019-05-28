## [ASP.NET](https://docs.microsoft.com/en-us/aspnet/index#pivot=aspnet)

# ASP.NET MVC Pipeline

[ASP.NET MVC: The Request-Handling Pipeline](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/blob/master/Pictures/asp_net_mvc_poster.pdf)

##

[Lifecycle of an ASP.NET.MVC 5 Aapplication](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/blob/master/Pictures/lifecycle-of-an-aspnet-mvc-5-application.pdf)

## 

![ASP.NET MVC pipline](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/blob/master/Pictures/ASP.NET.MVC.5.Pipeline.png)

# ASP.NET MVC (github)

  - [ASP.NET MVC 5.x, Web API 2.x, and Web Pages 3.x (not ASP.NET Core)](https://github.com/aspnet/AspNetWebStack)
  
## Tasks

0. (deadline - 02.06.2019) Добавить в проект для работы с банковским счетом - [Task 2](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/blob/master/Days%2023-24%20-%2010.05.2019/README.md) - уровень представления на основе ASP.NET MVC.

1. Реализовать кастомный обработчик запроса - [IHttpHandler](https://docs.microsoft.com/en-us/dotnet/api/system.web.ihttphandler?view=netframework-4.7.2), который возвращает изображение, находящееся в некотором каталоге приложения.
  
2. Реализовать кастомный обработчик маршрута - [IRouteHandler](https://docs.microsoft.com/en-us/dotnet/api/system.web.routing.iroutehandler?view=netframework-4.7.2), который используется для обработки маршрута c URL-паттерном **Image/{id}** и устанавливает для дальнейшей обработки запроса IHttpHandler из п.1.
  
  Примеры ниже.
   ### ![](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/blob/master/Pictures/1.png)
    
   ### ![](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/blob/master/Pictures/2.png)
    
   ### ![](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/blob/master/Pictures/3.png)
  
  3. Реализовать кастомный управляемый модуль - [IHttpModule](https://docs.microsoft.com/en-us/dotnet/api/system.web.ihttpmodule?view=netframework-4.7.2), который, в случае, если данные маршрута предоставляются согласно  URL-паттерну **Image/{id}**, предоставляет в качестве обработчика запроса IHttpHandler из п.1. Примеры запроса выглядят аналогично п. 2.


### [Репозиторий вопросов и ответов](https://github.com/AnzhelikaKravchuk/.NET-Training.-Spring-2019/tree/master/.Net-Interview-Questions)

![](https://github.com/AnzhelikaKravchuk/Materials/blob/master/Pictures/Q%26A.png)
