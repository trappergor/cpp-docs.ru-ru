---
title: Ошибка компилятора C2603
ms.date: 11/04/2016
f1_keywords:
- C2603
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
ms.openlocfilehash: e4540180058c890a1dec9c4060f796f1f044c934
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447992"
---
# <a name="compiler-error-c2603"></a>Ошибка компилятора C2603

> "*функция*": Слишком много статических объектов блок область с конструкторами и деструкторами в функции

В версиях Microsoft C++ компилятора до Visual Studio 2015, или когда [/Zc: threadsafeinit](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) указан параметр компилятора, не более 31 число статических объектов может иметь в видимое извне Встроенная функция.

Чтобы устранить эту проблему, рекомендуется применять более новая версия Microsoft C++ набор инструментов компилятора, или если это возможно, удалите параметр компилятора/Zc: threadsafeinit. Если это невозможно, рассмотрите возможность объединения статических объектов. Если объекты имеют тот же тип, можно использовать один статический массив этого типа и ссылаться на отдельные элементы при необходимости.

## <a name="example"></a>Пример

Следующий код приводит к возникновению ошибки C2603 и показан один из способов ее устранения:

```cpp
// C2603.cpp
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };
extern inline void f1() {
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;
    static C C32;   // C2603 Comment this line out to avoid error
}
```
