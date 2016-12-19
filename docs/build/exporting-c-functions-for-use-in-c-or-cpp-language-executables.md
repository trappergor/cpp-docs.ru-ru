---
title: "Экспорт функций на языке C для использования в исполняемых файлах, исходный код которых написан на языке C или C++ | Microsoft Docs"
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
  - "__cplusplus - макрос"
  - "экспорт библиотек DLL [C++], Функции C++ в реализации C"
  - "функции - экспортирование [C++], Функции C++ в реализации C"
  - "функции [C], реализация C или C++ и"
  - "функции [C], экспорт"
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Экспорт функций на языке C для использования в исполняемых файлах, исходный код которых написан на языке C или C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если в библиотеке DLL есть функции, написанные на языке C, к которым необходимо обращаться из модуля на языке C или C\+\+, следует использовать макрос препроцессора **\_\_cplusplus** для определения компилируемого языка, а затем необходимо объявить эти функции с компоновкой C, если используется модуль на C\+\+.  Если использовать этот метод и предоставить файлы заголовка для библиотеки DLL, эти функции без изменений смогут использовать пользователи C и C\+\+.  
  
 В следующем примере кода показан, файл заголовка, который могут использовать клиентские приложения на C и C\+\+.  
  
```  
// MyCFuncs.h  
#ifdef __cplusplus  
extern "C" {  // only need to export C interface if  
              // used by C++ source code  
#endif  
  
__declspec( dllimport ) void MyCFunc();  
__declspec( dllimport ) void AnotherCFunc();  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
 Если требуется привязать функции на C к исполняемому файлу на C\+\+, а в файлах заголовка не использовался метод объявления функции, описанный выше, в исходном файле на C\+\+ необходимо выполнить следующие действия, чтобы компилятор не изменил имена функций на C:  
  
```  
extern "C" {  
#include "MyCHeader.h"  
}  
```  
  
## Выберите действие.  
  
-   [Экспорт из библиотеки DLL с использованием DEF\-файлов](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с использованием \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт и импорт с использованием AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Определение подходящего метода экспорта](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с использованием \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Инициализацию DLL](../build/initializing-a-dll.md)  
  
## Дополнительные сведения  
  
-   [Декорированные имена](../Topic/Decorated%20Names.md)  
  
-   [Спецификации компоновки](http://msdn.microsoft.com/ru-ru/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## См. также  
 [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)