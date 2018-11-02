---
title: Ошибка компилятора C2603
ms.date: 11/04/2016
f1_keywords:
- C2603
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
ms.openlocfilehash: 5391aed09b7fd448a9d72ea7cc17cd5c26fc5f04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605768"
---
# <a name="compiler-error-c2603"></a>Ошибка компилятора C2603

> "*функция*": слишком много статических объектов блок область с конструкторами и деструкторами в функции

В версии компилятора Visual C++ до Visual Studio 2015 или когда [/Zc: threadsafeinit](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) указан параметр компилятора, не более 31 число статических объектов может иметь в доступном встроенной функции .

Чтобы устранить эту проблему, рекомендуется применять более новая версия набора инструментов компилятора Visual C++, или если это возможно, удалите параметр компилятора/Zc: threadsafeinit. Если это невозможно, рассмотрите возможность объединения статических объектов. Если объекты имеют тот же тип, можно использовать один статический массив этого типа и ссылаться на отдельные элементы при необходимости.

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
