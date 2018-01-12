---
title: "Вызов функций библиотек DLL из приложений Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed99b0ebe41a8f1bc9684638fa74e18556dd51f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>Вызов функций библиотек DLL из приложений Visual Basic
Для приложений Visual Basic (или приложений в других языках, например Pascal или Fortran) для вызова функций в библиотеке DLL C/C++ функции необходимо экспортировать с помощью правильное соглашение о вызовах без декорирования имен компилятором.  
  
 `__stdcall`Создает правильное соглашение о вызовах функции (вызываемая функция очищает стек, а параметры передаются справа налево), но по-разному декорирует имя функции. Поэтому, если **__declspec(dllexport)** используется в экспортированной функции в DLL, экспортируется декорированного имени.  
  
 `__stdcall` Декорирование имен префиксы имени символа подчеркивания (_) и добавляет символ с символа (@) символ, а затем число байтов в списке аргументов (требуемый размер стека). Таким образом, функция, объявленная как:  
  
```  
int __stdcall func (int a, double b)  
```  
  
 помечено как:  
  
```  
_func@12  
```  
  
 Соглашение о вызовах языка C (`__cdecl`) экспортируемое имя как `_func`.  
  
 Чтобы получить декорированное имя, используйте [/MAP](../build/reference/map-generate-mapfile.md). Использование **__declspec(dllexport)** делает следующее:  
  
-   Если функция экспортируется с соглашение о вызовах языка C (**_cdecl**), при экспорте имени удаляются символа подчеркивания (_).  
  
-   Если экспортируемая функция не использует соглашение о вызовах языка C (например, `__stdcall`), команда экспортирует декорированного имени.  
  
 Поскольку нет возможности переопределить порядок очистки стека, необходимо использовать `__stdcall`. Декорированное имена с `__stdcall`, необходимо указать их с помощью псевдонимов в разделе EXPORTS DEF-файла. Это показано ниже для в следующем объявлении функции:  
  
```  
int  __stdcall MyFunc (int a, double b);  
void __stdcall InitCode (void);  
```  
  
 В. DEF-файл:  
  
```  
EXPORTS  
   MYFUNC=_MyFunc@12  
   INITCODE=_InitCode@0  
```  
  
 В DEF-файл для библиотеки DLL, вызываемой программы, написанные на языке Visual Basic, требуется технику псевдонимов, описанную в этом разделе. Если псевдоним создается в программе Visual Basic, необязательно создавать псевдоним в DEF-файл. Он может выполняться в программе Visual Basic, добавив предложение псевдоним для [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement) инструкции.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)  
  
-   [Экспорт из библиотеки DLL с помощью. DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с помощью __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт функций C++ для использования в исполняемых файлах языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Определение подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)  
  
-   [Внутренние имена](../build/reference/decorated-names.md)  
  
## <a name="see-also"></a>См. также  
 [DLL в Visual C++](../build/dlls-in-visual-cpp.md)