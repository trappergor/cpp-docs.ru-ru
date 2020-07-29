---
title: Выгрузка библиотеки DLL, загруженной с задержкой
ms.date: 11/04/2016
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
ms.openlocfilehash: 1895bf12cb195ef7b4555d400badf112d377547b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211922"
---
# <a name="unloading-a-delay-loaded-dll"></a>Выгрузка библиотеки DLL, загруженной с задержкой

Предоставленный по умолчанию вспомогательный модуль отложенной загрузки проверяет, имеют ли дескрипторы с отложенной загрузкой указатель и копию исходной таблицы адресов импорта (IAT) в поле Пунлоадиат. Если да, то он сохранит указатель в списке на дескриптор задержки импорта. Это позволяет вспомогательной функции найти библиотеку DLL по имени, чтобы обеспечить явное выгрузку этой библиотеки DLL.

Ниже приведены связанные структуры и функции для явной загрузки библиотеки DLL с отложенной загрузкой.

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

Структура Унлоадинфо реализуется с помощью класса C++, который использует реализации **локалаллок** и **функции LocalFree** в качестве оператора **`new`** и оператора **`delete`** соответственно. Эти параметры хранятся в стандартном связанном списке с использованием __puiHead в качестве заголовка списка.

При вызове __FUnloadDelayLoadedDLL будет предпринята попытка найти имя, которое вы задаете в списке загруженных библиотек DLL (требуется точное совпадение). Если объект найден, копия IAT в Пунлоадиат копируется в верхней части выполняющейся IAT для восстановления указателей преобразователей, Библиотека освобождается с помощью **FreeLibrary**, соответствующая запись **унлоадинфо** удаляется из списка и удаляется, а возвращается значение true.

Аргумент функции __FUnloadDelayLoadedDLL2 с учетом регистра. Например, можно указать:

```cpp
__FUnloadDelayLoadedDLL2("user32.DLL");
```

не так:

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>См. также раздел

[Основные сведения о вспомогательной функции](understanding-the-helper-function.md)
