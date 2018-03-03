---
title: "Импорт и экспорт встроенных функций | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6f8d159a1537cdfee02d45805632ba9ad4afa7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="importing-and-exporting-inline-functions"></a>Импорт и экспорт встраиваемых функций
Импортируемых функций можно определить как встроенную. Результат является примерно таким же, как определение стандартной встроенной функции; вызовы функции разворачиваются во встроенный код, подобно макроса. В основном применяется, как средства поддержки C++ классов в библиотеке DLL, могут встраиваться некоторые члены функции для повышения эффективности.  
  
 Одной из особенностей импортируемой встроенной функции заключается в том, что может потребоваться его адрес в C++. Компилятор возвращает адрес копии встроенной функции, находящейся в библиотеке DLL. Другой возможностью импортированных встроенных функций является возможность инициализации статических локальных данных импортированной функции, в отличие от глобальных импортируемых данных.  
  
> [!CAUTION]
>  Следует соблюдать осторожность при передаче импортируемых встроенных функций, поскольку они могут вызвать конфликты версий. Встроенная функция разворачивается в код приложения; Таким образом Если функция написан позже, оно обновится, если не перекомпилируется самого приложения. (Как правило, функции библиотеки DLL можно обновить без повторного построения приложений, которые их используют.)  
  
## <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)  
  
-   [Экспорт из библиотеки DLL с помощью. DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с помощью __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт и импорт с использованием AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Экспорт функций C++ для использования в реализации языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Выбор подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с помощью __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
## <a name="see-also"></a>См. также  
 [Импортирование и экспортирование](../build/importing-and-exporting.md)