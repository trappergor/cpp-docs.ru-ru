---
title: "Экспорт функций C++ для использования в исполняемых файлах языка C | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C++], C++ functions in C executables
- exporting DLLs [C++], C++ functions in C executables
- exporting functions [C++], C++ functions in C executables
- functions [C++], exporting
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 56e275b6c97bf319ab3d2bacb014423e6c0efd20
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="exporting-c-functions-for-use-in-c-language-executables"></a>Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C  
  
Если есть функции в DLL, написанным на языке C++, которым требуется доступ из модуля языка C, следует объявить эти функции с компоновкой C, а не C++. Если не указано иное, компилятор C++ использует C++ типобезопасный именования (оформление имен) и C++, соглашения о вызовах, которые трудно реализовать средствами языка C.  
  
Чтобы указать компоновку C, укажите `extern "C"` объявлениях функций. Пример:  
  
```  
extern "C" __declspec( dllexport ) int MyFunc(long parm1);  
```  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Экспорт из библиотеки DLL с использованием DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с помощью __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Выбор подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с помощью __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Внутренние имена](../build/reference/decorated-names.md)  
  
-   [Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)  
  
## <a name="see-also"></a>См. также  
 [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)