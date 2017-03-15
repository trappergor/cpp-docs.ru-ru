---
title: "Экспорт из библиотеки DLL с использованием __declspec(dllexport) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dllexport"
  - "__declspec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllexport) - ключевое слово [C++]"
  - "директивы экспорта [C++]"
  - "экспорт библиотек DLL [C++], __declspec(dllexport) - ключевое слово"
  - "имена [C++], DLL - экспорт"
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Экспорт из библиотеки DLL с использованием __declspec(dllexport)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В 16\-разрядной версии компилятора Visual C\+\+ Майкрософт ввел понятие **\_\_export**, которое позволяет компилятору автоматически создавать экспортируемые имена функций и помещать их в LIB\-файл.  Затем LIB\-файл используется для связи с библиотекой DLL, однако следует отметить, что LIB\-файл является статическим.  
  
 В новых версиях компилятора экспорт данных, функций, классов или классов функций\-членов из библиотеки DLL можно осуществлять с помощью ключевого слова **\_\_declspec\(dllexport\)**.  Ключевое слово **\_\_declspec\(dllexport\)** добавляет директивы экспорта в объектный файл, следовательно, отпадает необходимость использовать DEF\-файл.  
  
 Данное преимущество особенно заметно при экспорте декорированных имен функций C\+\+.  Так как стандарта спецификации по декорированию имен функции не существует, то имя экспортируемой функции может отличаться в зависимости от версии компилятора.  Если используется ключевое слово **\_\_declspec\(dllexport\)**, перекомпиляция библиотеки DLL и EXE\-файлов необходима только для регистрации изменений в соглашениях об именах.  
  
 Большинство директив экспорта, например, NONAME и PRIVATE, можно указать только в DEF\-файле, других способов указания данных атрибутов без использования DEF\-файла не существует.  Однако если наряду с DEF\-файлом используется **\_\_declspec\(dllexport\)**, ошибок при построении не будет.  
  
 Чтобы экспортировать функции, ключевое слово **\_\_declspec\(dllexport\)** должно стоять слева от ключевого слова соглашения о вызовах, если оно задано.  Примеры.  
  
```  
__declspec(dllexport) void __cdecl Function1(void);  
```  
  
 Чтобы экспортировать все общие члены данных и функции\-члены в класс, ключевое слово должно стоять слева от имени класса:  
  
```  
class __declspec(dllexport) CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
> [!NOTE]
>  `__declspec(dllexport)` нельзя применить к функции с соглашением о вызовах `__clrcall`.  
  
 При построении библиотеки DLL, как правило, создается файл заголовка, который содержит прототипы функций и \(или\) экспортируемые классы, а также объявления с ключевым словом **\_\_declspec\(dllexport\)**.  Чтобы сделать код более удобочитаемым, можно для **\_\_declspec\(dllimport\)** определить макрос и использовать его для объявления каждого импортируемого символа:  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **\_\_declspec\(dllexport\)** сохраняет имена функций в таблице экспорта библиотеки DLL.  Сведения по оптимизации таблицы размеров можно посмотреть в разделе [Экспорт функций из библиотеки DLL по порядку, а не по имени](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
> [!NOTE]
>  При переносе исходного кода библиотеки DLL с Win16 на Win32 необходимо заменить каждый экземпляр **\_\_export** ключевым словом **\_\_declspec\(dllexport\)**.  
  
 Для получения справки можно в файле заголовка Winbase.h выполнить поиск по слову "Win32".  Там же можно найти примеры использования **\_\_declspec\(dllimport\)**.  
  
## Выберите действие.  
  
-   [Экспорт из библиотеки DLL с использованием DEF\-файлов](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт и импорт с использованием AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Экспорт функций C\+\+ для использования в исполняемых файлах, исходный код которых написан на языке C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Экспорт функций на языке C для использования в файлах, исходный код которых написан на языке C или C\+\+](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Определение подходящего метода экспорта](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с использованием \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Инициализацию DLL](../build/initializing-a-dll.md)  
  
## Дополнительные сведения  
  
-   [Ключевое слово \_\_declspec](../cpp/declspec.md)  
  
-   [Импорт и экспорт встроенных функций](../Topic/Importing%20and%20Exporting%20Inline%20Functions.md)  
  
-   [Взаимный импорт](../Topic/Mutual%20Imports.md)  
  
## См. также  
 [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)