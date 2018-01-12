---
title: "Экспорт из библиотеки DLL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exporting DLLs [C++], about exporting from DLLs
- exporting functions [C++], DLLs (exporting from)
- exporting DLLs [C++]
- DLLs [C++], exporting from
- DLL exports [C++]
- functions [C++], exporting
- exports table [C++]
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64571a0f648c0e33635990d9ca57744877429049
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-from-a-dll"></a>Экспорт из библиотеки DLL  
  
DLL-файл имеет очень похожа на файл .exe с одним важным отличием — DLL-файл содержит таблицу экспорта. Таблицу экспорта содержит имя каждой функции, библиотека DLL экспортирует в другие исполняемые файлы. Эти функции являются точками входа в библиотеку DLL. только функции в таблице экспорта может осуществляться других исполняемых файлов. Другие функции в DLL-Библиотеке являются закрытыми для библиотеки DLL. Таблицу экспорта библиотеки DLL можно просмотреть с помощью [DUMPBIN](../build/reference/dumpbin-reference.md) средство с параметром/EXPORTS.  
  
 Можно экспортировать функции из библиотеки DLL с помощью двух методов:  
  
-   Создание файла определения модуля (DEF) и использовать данный файл при построении библиотеки DLL. Используйте этот подход, если вы хотите [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
-   Используйте ключевое слово **__declspec(dllexport)** в определении функции.  
  
 При экспорте функции другого метода, убедитесь, что для использования [__stdcall](../cpp/stdcall.md) соглашение о вызовах.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Экспорт из библиотеки DLL с использованием DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с помощью __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Экспорт функций C++ для использования в реализации языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)  
  
-   [Выбор подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)  
  
-   [Определение подходящего метода связывания](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
-   [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Импорт в приложение](../build/importing-into-an-application.md)  
  
-   [Импорт и экспорт встроенных функций](../build/importing-and-exporting-inline-functions.md)  
  
-   [Взаимный импорт](../build/mutual-imports.md)  
  
## <a name="see-also"></a>См. также  
 [Импортирование и экспортирование](../build/importing-and-exporting.md)