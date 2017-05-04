---
title: "Справочник по языку C++ (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
caps.latest.revision: 27
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 27
---
# Справочник по языку C++ (C++/CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) — это набор расширений языка C\+\+, позволяющий создавать приложения для Windows и компоненты [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] с идиоматикой, максимально близкой к современному C\+\+. Используйте [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] для написания приложений для Windows и компонентов в машинном коде, легко взаимодействующих с Visual C\#, Visual Basic и JavaScript, а также другими языками, поддерживающими [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. В редких случаях, когда требуется прямой доступ к интерфейсам COM или код без поддержки исключений, можно использовать [Библиотека шаблонов C\+\+ среды выполнения Windows \(WRL\)](http://msdn.microsoft.com/library/b915afce-553b-44a7-b8dc-0ab601758eb0).  
  
 Новая модель представляет следующее поколение средств создания машинного кода для Windows в C\+\+. С его помощью можно создавать:  
  
-   Приложения C\+\+ для Windows, в которых пользовательский интерфейс определяется с помощью XAML\-кода и используется собственный стек. Дополнительные сведения см. в статье [Создание приложения "hello world" на C\+\+ \(Windows 10\)](http://msdn.microsoft.com/library/windows/apps/dn996906.aspx).  
  
-   Компоненты C\+\+ [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], которые могут использоваться приложениями для Windows на базе JavaScript. Дополнительные сведения см. в статье [Создание компонентов среды выполнения Windows на C\+\+](http://msdn.microsoft.com/library/hh441569.aspx)[Создание компонентов среды выполнения Windows в C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
-   Игры Windows на базе DirectX и приложения, активно использующие графику. Дополнительные сведения см. в статье [Создание простой игры на универсальной платформе Windows \(UWP\) на базе DirectX](http://msdn.microsoft.com/library/windows/apps/xaml/mt210793.aspx).  
  
## Связанные статьи  
  
|||  
|-|-|  
|[Краткий справочник](../cppcx/quick-reference-c-cx.md)|Таблица ключевых слов и операторов для [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\).|  
|[Система типов](../cppcx/type-system-c-cx.md)|Базовые типы и программные конструкции [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], а также принципы использования и создания типов [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] с помощью [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].|  
|[Построение приложений и библиотек](../cppcx/building-apps-and-libraries-c-cx.md)|Принципы использования интегрированной среды разработки для построения приложений и подключения статических библиотек и DLL.|  
|[Взаимодействие с другими языками](../cppcx/interoperating-with-other-languages-c-cx.md)|Принципы использования компонентов, написанных с помощью [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], с компонентами, написанными на языке JavaScript, любом управляемом языке или с помощью [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)].|  
|[Работа с потоками и маршалинг](../cppcx/threading-and-marshaling-c-cx.md)|Принципы указания поведения при использовании потоков и маршалинга в создаваемых компонентах.|  
|[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)|Справочная документация по следующим пространствам имен: по умолчанию, Platform, Platform::Collections и другим связанным с ними пространствам имен.|  
|[Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Список функций CRT, недоступных для использования в приложениях среды выполнения Windows.|  
|[Практические руководства по приложениям Windows 10](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Общие рекомендации по приложениям Windows 10, а также ссылки на дополнительную информацию.|  
  
1.  [C\+\+\/CX: часть 0 из \[n\]. Введение](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
2.  [C\+\+\/CX: часть 0 из \[n\]. Введение](http://blogs.msdn.com/b/vcblog/archive/2012/08/29/cxxcxpart00anintroduction.aspx)  
  
3.  [C\+\+\/CX: часть 2 из \[n\]. Типы с крышками](http://blogs.msdn.com/b/vcblog/archive/2012/09/17/cxxcxpart02typesthatwearhats.aspx)  
  
4.  [C\+\+\/CX: часть 3 из \[n\]. В разработке](http://blogs.msdn.com/b/vcblog/archive/2012/10/05/cxxcxpart03underconstruction.aspx)  
  
5.  [C\+\+\/CX: часть 4 из \[n\]. Статические функции\-члены](http://blogs.msdn.com/b/vcblog/archive/2012/10/19/cxxcxpart04staticmemberfunctions.aspx)