---
title: "Изменения в библиотеке DLL вспомогательной функции отложенной загрузки с Visual C++ 6.0 | Документы Microsoft"
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
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3123a722e0e95119a4b04f5c060bd947b987cdf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>Изменения вспомогательной функции отложенной загрузки библиотек DLL по сравнению с Visual C++ версии 6.0
Если на компьютере имеется несколько версий Visual C++, или если вы определили собственную вспомогательную функцию, вы может затронуть изменения, внесенные в библиотеки DLL вспомогательной функции отложенной загрузки. Пример:  
  
-   **__delayLoadHelper** теперь **__delayLoadHelper2**  
  
-   **__pfnDliNotifyHook** теперь **__pfnDliNotifyHook2**  
  
-   **__pfnDliFailureHook** теперь **__pfnDliFailureHook2**  
  
-   **__FUnloadDelayLoadedDLL** теперь **__FUnloadDelayLoadedDLL2**  
  
> [!NOTE]
>  Если вы используете функцию по умолчанию, эти изменения не повлияют вы. Существуют изменения, связанные со способом вызова компоновщика.  
  
## <a name="multiple-versions-of-visual-c"></a>Несколько версий Visual C++  
 Если имеется несколько версий Visual C++ на компьютере, убедитесь, что компоновщик соответствует библиотекой delayimp.lib. Если имеется несоответствие, возникнет ошибка компоновщика, сообщающая, либо `___delayLoadHelper2@8` или `___delayLoadHelper@8` как неразрешенный внешний символ. Другими словами, новый компоновщик используется со старой библиотекой delayimp.lib, а второе означает, что старый компоновщик используется с новой библиотекой delayimp.lib.  
  
 Если вы получаете Неустранимая ошибка компоновщика, запустите [dumpbin/LINKERMEMBER](../../build/reference/linkermember.md): 1 на библиотекой delayimp.lib, которые будут содержать вспомогательную функцию, чтобы увидеть, какие вспомогательная функция задана. Вспомогательная функция также могли быть заданы в объектном файле; Запустите [dumpbin/Symbols](../../build/reference/symbols.md) и выполните поиск `delayLoadHelper(2)`.  
  
 Если вы знаете, что у вас есть компоновщик Visual C++ 6.0, затем:  
  
-   Запустите программу dumpbin на вспомогательный нагрузки задержки lib или OBJ файл, чтобы определить, является ли он определяет **__delayLoadHelper2**. В противном случае произойдет сбой по ссылке.  
  
-   Определение **__delayLoadHelper** в задержки загрузки файла LIB или OBJ помощника.  
  
## <a name="user-defined-helper-function"></a>Определяемые пользователем вспомогательной функции  
 Если определен собственной вспомогательной функции и текущей версии Visual C++, выполните следующее:  
  
-   Вспомогательная функция, чтобы переименовать **__delayLoadHelper2**.  
  
-   Поскольку на относительные адреса (RVA) работать должным образом в обеих программах 32 - и 64-разрядных указателей дескриптора задержки (ImgDelayDescr в delayimp.h) из абсолютного адреса (VA) были изменены, необходимо преобразовать их обратно в указатели. Представлена новая функция: PFromRva, найден в delayhlp.cpp. Эта функция используется для всех полей в дескрипторе преобразовать их обратно в указатели либо 32 - или 64-разрядная версия. Вспомогательную функцию отложенной загрузки по умолчанию по-прежнему можно использовать в качестве примера.  
  
## <a name="load-all-imports-for-a-delay-loaded-dll"></a>Загрузка всех импортов для библиотеки DLL, загружаемых с задержкой  
 Компоновщик может загружать все импорты из библиотеки DLL, который указан с отложенной загрузкой. В разделе [загрузка всех импортов для библиотеки DLL Delay-Loaded](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [Понятие вспомогательной функции](understanding-the-helper-function.md)