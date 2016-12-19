---
title: "Экспорт из библиотеки DLL | Microsoft Docs"
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
  - "DLL - экспорт [C++]"
  - "DLL-библиотеки [C++], экспортирование из"
  - "экспорт библиотек DLL [C++]"
  - "экспорт библиотек DLL [C++], сведения об экспортировании из библиотек DLL"
  - "функции - экспортирование [C++], библиотеки DLL (экспортирование из)"
  - "таблица экспортов [C++]"
  - "функции [C++], экспорт"
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Экспорт из библиотеки DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Структура файла библиотеки DLL очень похожа на структуру EXE\-файла с одним важным отличием: файл библиотеки DLL содержит таблицу экспорта.  Таблица экспорта содержит имя каждой функции, которую библиотека DLL экспортирует в другие исполняемые файлы.  Эти функции являются точками входа в библиотеку DLL. Другим исполняемым файлам доступны только те функции, которые представлены в таблице экспорта.  Все остальные функции принадлежат только самой библиотеке DLL.  Таблицу экспорта библиотеки DLL можно просмотреть с помощью утилиты [DUMPBIN](../build/reference/dumpbin-reference.md) с параметром \/EXPORTS.  
  
 Существует два метода экспорта функций из библиотеки DLL:  
  
-   Создать файл определения модуля \(DEF\-файл\) и использовать данный файл при построении библиотеки DLL.  Данный метод необходимо использовать в случае, когда требуется [экспортировать функции из библиотеки DLL по порядковому номеру, а не по имени](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
-   Использовать ключевое слово **\_\_declspec\(dllexport\)** в определении функции.  
  
 При использовании для экспорта функции другого метода, убедитесь в том, что используется соглашение о вызове [\_\_stdcall](../cpp/stdcall.md).  
  
## Выберите действие.  
  
-   [Экспорт из библиотеки DLL с использованием DEF\-файлов](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с использованием \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт и импорт с использованием AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Экспорт функций C\+\+ для использования в исполняемых файлах, исходный код которых написан на языке C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Экспорт функций на языке C для использования в файлах, исходный код которых написан на языке C или C\+\+](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Экспорт функции из библиотеки DLL по порядковому номеру, а не по имени](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)  
  
-   [Определение подходящего метода экспорта](../build/determining-which-exporting-method-to-use.md)  
  
-   [Определение подходящего метода связывания](../build/determining-which-linking-method-to-use.md)  
  
-   [Инициализацию DLL](../build/initializing-a-dll.md)  
  
## Дополнительные сведения  
  
-   [Импорт в приложение](../build/importing-into-an-application.md)  
  
-   [Импорт и экспорт встроенных функций](../Topic/Importing%20and%20Exporting%20Inline%20Functions.md)  
  
-   [Взаимный импорт](../Topic/Mutual%20Imports.md)  
  
## См. также  
 [Импортирование и экспортирование](../build/importing-and-exporting.md)