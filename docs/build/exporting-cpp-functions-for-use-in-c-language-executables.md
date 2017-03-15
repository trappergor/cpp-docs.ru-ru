---
title: "Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "экспорт библиотек DLL [C++], Функции C++ в реализации C"
  - "функции - экспортирование [C++], Функции C++ в реализации C"
  - "функции [C++], Функции C++ в реализации C"
  - "функции [C++], экспорт"
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если к функциям в библиотеках DLL, исходный код которых написан на языке C\+\+, требуется доступ из модуля, написанного на языке C, то эти функции следует объявить с помощью компоновки C, а не C\+\+.  Если не указано иное, компилятор C\+\+ использует типобезопасное именование C\+\+ \(или оформление имен\), а также соглашения о вызовах C\+\+, которые трудно реализовать средствами языка C.  
  
 Чтобы указать компоновку C, в объявлениях функций укажите **extern**"**C**".  Примеры.  
  
```  
extern "C" __declspec( dllexport ) int MyFunc(long parm1);  
```  
  
## Выберите действие.  
  
-   [Экспорт из библиотеки DLL с использованием DEF\-файлов](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с использованием \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт и импорт с использованием AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Экспорт функций на языке C для использования в файлах, исходный код которых написан на языке C или C\+\+](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Определение подходящего метода экспорта](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с использованием \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Инициализацию DLL](../build/initializing-a-dll.md)  
  
## Дополнительные сведения  
  
-   [Декорированные имена](../Topic/Decorated%20Names.md)  
  
-   [Спецификации компоновки](http://msdn.microsoft.com/ru-ru/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## См. также  
 [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)