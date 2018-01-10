---
title: "Экспорт функций на языке C для использования в C или исполняемые файлы языка C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C], exporting
- functions [C], C or C++ executables and
- __cplusplus macro
- exporting DLLs [C++], C functions in C++ executables
- exporting functions [C++], C functions in C++ executables
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 232cfb3a65dfe3e65eaa2eeef0a4a55e723b7f7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-c-functions-for-use-in-c-or-c-language-executables"></a>Экспорт функций на языке C для использования в исполняемых файлах, исходный код которых написан на языке C или C++  
  
При наличии функций в библиотеке DLL, написанный на языке C, которым требуется доступ из языка C или C++ языкового модуля, следует использовать **__cplusplus** макрос препроцессора, чтобы определить, какой язык компилируется и затем объявите их функции с компоновкой C, если используется модуль на C++. Если использовать этот метод и предоставить файлы заголовка для библиотеки DLL, эти функции могут использоваться пользователями C и C++ без изменения.  
  
В следующем коде показано файл заголовка, который может использоваться клиентскими приложениями C и C++:  
  
```h  
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
  
Если необходимо связать функции C C++ исполняемые файлы заголовков объявление функции не имеют использовать метод выше, в файле исходного кода C++, выполните следующую команду, чтобы запретить компилятору декорирования имена функций C:  
  
```cpp  
extern "C" {  
#include "MyCHeader.h"  
}  
```  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Экспорт из библиотеки DLL с использованием DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с помощью __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Выбор подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с помощью __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Внутренние имена](../build/reference/decorated-names.md)  
  
-   [Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)  
  
## <a name="see-also"></a>См. также  
 [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)