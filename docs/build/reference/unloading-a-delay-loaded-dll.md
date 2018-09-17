---
title: Выгрузка библиотеки DLL с отложенной загрузкой | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa7b9652c37b6c4e841a798dae3cfeb69779b5ff
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719931"
---
# <a name="unloading-a-delay-loaded-dll"></a>Выгрузка библиотеки DLL, загруженной с задержкой

Вспомогательный метод отложенной загрузки, предоставляемая по умолчанию проверяет дескрипторы отложенной загрузки ли указатель и копия исходной таблицы адресов импорта (IAT) в поле pUnloadIAT. Если Да, указатель будет сохраняться в списке, чтобы дескриптора задержки импорта. Это позволяет вспомогательную функцию для поиска библиотеки DLL по имени, чтобы поддерживать выгрузку библиотеки DLL явным образом.

Ниже приведены, связанные с ними структуры и функции для явная выгрузка библиотеки DLL, загружаемых с задержкой.

```cpp
//
// Unload support from delayimp.h
//

// routine definition; takes a pointer to a name to unload

ExternC
BOOL WINAPI
__FUnloadDelayLoadedDLL2(LPCSTR szDll);

// structure definitions for the list of unload records
typedef struct UnloadInfo * PUnloadInfo;
typedef struct UnloadInfo {
    PUnloadInfo     puiNext;
    PCImgDelayDescr pidd;
    } UnloadInfo;

// from delayhlp.cpp
// the default delay load helper places the unloadinfo records in the
// list headed by the following pointer.
ExternC
PUnloadInfo __puiHead;
```

Структура UnloadInfo реализуется с помощью класса C++, использующий **LocalAlloc** и **LocalFree** в реализации своего оператора **новый** и оператор  **Удалить** соответственно. Эти параметры хранятся в стандартных связанного списка с помощью __puiHead как начало списка.

Вызов __FUnloadDelayLoadedDLL будет найти имя вами в список загружаемые DLL (точное совпадение не требуется). Если найден, копия IAT в pUnloadIAT копируется поверх работающей IAT, чтобы восстановить указатели преобразователя библиотеки освобождается с **FreeLibrary**, соответствующий **UnloadInfo** записи не будет связан с список и удаляются и возвращается значение TRUE.

Аргумент функции __FUnloadDelayLoadedDLL2 чувствительно к регистру. Например следует указать:

```cpp
__FUnloadDelayLoadedDLL2("user32.DLL");
```

но не:

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>См. также

[Понятие вспомогательной функции](understanding-the-helper-function.md)