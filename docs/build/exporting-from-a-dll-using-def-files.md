---
title: Экспорт из библиотеки DLL с использованием DEF-файлы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
- exporting DLLs [C++], DEF files
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a870df7ea803813a8403cd807c0f0612873d4576
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="exporting-from-a-dll-using-def-files"></a>Экспорт из библиотеки DLL с использованием DEF-файлов
Файл определения модуля (DEF) является текстовый файл, содержащий один или несколько операторов модуля, описывающих различные атрибуты библиотеки DLL. Если вы не используете **__declspec(dllexport)** ключевое слово для экспорта функций DLL, необходимой библиотеке DLL DEF-файла.  
  
 Минимальный DEF-файл должен содержать следующие инструкции определения модуля:  
  
-   Первый оператор в файле должен быть оператор LIBRARY. Этот оператор определяет DEF-файл как принадлежащий библиотеке DLL. Имя библиотеки DLL следует инструкцию БИБЛИОТЕКИ. Компоновщик помещает это имя в DLL-библиотека импорта.  
  
-   Оператор EXPORTS перечисляет имена и, при необходимости, порядковые номера функций, экспортируемых из библиотеки DLL. Назначение функции порядковое значение, за которым следует имя функции с символа (@) и номером. При указании порядковые номера, они должны быть в диапазоне от 1 до N, где N — число функций, экспортируемых из библиотеки DLL. Если вы хотите экспортировать функции по порядковому номеру, см. раздел [Экспорт функций из библиотеки DLL по порядковому номеру, а не по имени](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) а также в этом разделе.  
  
 Например DLL, которая содержит код для реализации дерева двоичный поиск может выглядеть следующим образом:  
  
```  
LIBRARY   BTREE  
EXPORTS  
   Insert   @1  
   Delete   @2  
   Member   @3  
   Min   @4  
```  
  
 Если вы используете [мастера библиотек DLL MFC](../mfc/reference/mfc-dll-wizard.md) для создания библиотеки DLL MFC, мастер создает скелет DEF-файла и автоматически добавляет его в проект. Добавьте имена функций для экспорта в этот файл. Для не - библиотеки DLL MFC, необходимо создать DEF-файл самостоятельно и добавить его в проект.  
  
 При экспорте функции в файл C++ необходимо поместить декорированные имена в DEF-файле, либо определить экспортируемые функции с помощью стандартных средств компоновки C с помощью extern «C». Если необходимо поместить декорированные имена в DEF-файле, их можно получить с помощью [DUMPBIN](../build/reference/dumpbin-reference.md) инструмент либо с помощью компоновщика [/MAP](../build/reference/map-generate-mapfile.md) параметр. Обратите внимание, что декорированные имена, созданные компилятором, зависят от компилятора. Если поместить декорированные имена, созданные компилятором Visual C++ в DEF-файл приложения, связанные с библиотекой DLL должны также быть построены с использованием та же версия Visual C++, чтобы декорированные имена в вызывающем приложении совпадали с экспортированными именами в .de библиотеки DLL файл f.  
  
 При создании [DLL расширения](../build/extension-dlls-overview.md), экспорт с помощью DEF-файла, поместите следующий код в начало и конец файлов заголовка, содержащих экспортируемые классы:  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 Эти строки убедитесь, что переменные MFC, предназначены для внутреннего использования или добавленных к классам экспорта (или импорта) из библиотеки DLL расширения MFC. Например, при создании производного класса с помощью `DECLARE_DYNAMIC`, макрос расширяется `CRuntimeClass` переменной-члена в класс. Если исключить эти четыре строки может привести к библиотеки DLL для компиляции или неправильно ссылку или вызывает ошибку, когда клиентское приложение связано с библиотекой DLL.  
  
 При построении библиотеки DLL, компоновщик использует DEF-файл для создания файла экспорта (EXP) и библиотека (.lib) импортируемого файла. Затем компоновщик использует файл экспорта для построения DLL-файла. Исполняемые файлы, которые неявно ссылаются на библиотеку DLL, ссылаются на библиотеку импорта при построении.  
  
 Обратите внимание, что MFC использует DEF-файлы для экспорта функций и классов из файла MFCx0.dll.  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Экспорт из библиотеки DLL с помощью __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Экспорт функций C++ для использования в реализации языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Выбор подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с помощью __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [DEF-файлы](../build/reference/module-definition-dot-def-files.md)  
  
-   [Правила для операторов определения модуля](../build/reference/rules-for-module-definition-statements.md)  
  
-   [Внутренние имена](../build/reference/decorated-names.md)  
  
-   [Импорт и экспорт встроенных функций](../build/importing-and-exporting-inline-functions.md)  
  
-   [Взаимный импорт](../build/mutual-imports.md)  
  
## <a name="see-also"></a>См. также  
 [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)