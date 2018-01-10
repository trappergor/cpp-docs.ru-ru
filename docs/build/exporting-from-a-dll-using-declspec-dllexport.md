---
title: "Экспорт из библиотеки DLL с помощью __declspec(dllexport) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- dllexport
- __declspec
dev_langs: C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51f20e47724a6d32dad014fbaf025cd283112c54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>Экспорт из библиотеки DLL с использованием __declspec(dllexport)
Представленные Microsoft **__export** в версии 16-разрядный компилятор Visual C++, чтобы разрешить или запретить компилятору автоматически создавать экспортируемые имена и помещать их в LIB-файл. Этот LIB-файл может использоваться как статический LIB-файл для связи с библиотекой DLL.  
  
 В новых версиях компилятора можно экспортировать данные, функции, классы или функции-члены класса из библиотеки DLL с помощью **__declspec(dllexport)** ключевое слово. **__declspec(dllexport)** добавляет директивы экспорта в объектный файл, поэтому необходимо использовать DEF-файла.  
  
 Данное преимущество особенно заметно при экспорте декорированных имен функций C++. Так как нет стандартной спецификации для Декорирование имен, экспортированной функции может быть изменено от версии компилятора. Если вы используете **__declspec(dllexport)**, повторной компиляции библиотеки DLL и .exe-файлов необходима только для учетной записи для изменений в соглашениях об именовании.  
  
 Большинство директив экспорта, например порядковые номера, NONAME и PRIVATE, можно указать только в DEF-файл, и нет возможности задавать эти атрибуты без DEF-файла. Однако использование **__declspec(dllexport)** наряду с использованием .def файла не вызывает ошибки построения.  
  
 Для экспорта функций, **__declspec(dllexport)** ключевое слово должно стоять слева от ключевого слова соглашения о вызовах, если оно задано. Пример:  
  
```  
__declspec(dllexport) void __cdecl Function1(void);  
```  
  
 Чтобы экспортировать все открытые члены данных и функции-члены в классе, ключевое слово должно стоять слева от имени класса следующим образом:  
  
```  
class __declspec(dllexport) CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
> [!NOTE]
>  `__declspec(dllexport)`не может применяться в функцию с `__clrcall` соглашение о вызовах.  
  
 При построении библиотеки DLL, обычно создается файл заголовка, который содержит прототипы функций или классов экспортируются и добавить **__declspec(dllexport)** к объявлениям в файле заголовка. Чтобы сделать код более удобочитаемым, определить макрос для **__declspec(dllexport)** и использовать его каждый символ, который экспортируется:  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **__declspec(dllexport)** хранилищ функции именами в таблице экспорта библиотеки DLL. Если вы хотите оптимизировать размер таблицы, см. раздел [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
> [!NOTE]
>  При переносе исходный код DLL из Win16 в Win32, замените каждый экземпляр **__export** с **__declspec(dllexport)**.  
  
 Как ссылка поиск в файле заголовка Win32 Winbase.h. Она содержит примеры **__declspec(dllimport)** использования.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Экспорт из библиотеки DLL с использованием DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Экспорт функций C++ для использования в реализации языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Выбор подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с помощью __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [__Declspec-ключевое слово](../cpp/declspec.md)  
  
-   [Импорт и экспорт встроенных функций](../build/importing-and-exporting-inline-functions.md)  
  
-   [Взаимный импорт](../build/mutual-imports.md)  
  
## <a name="see-also"></a>См. также  
 [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)