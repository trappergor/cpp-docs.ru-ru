---
title: Ошибка компилятора C2482
ms.date: 09/15/2017
f1_keywords:
- C2482
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
ms.openlocfilehash: 481920fa2d8c32bc872e7b8805188cc674e6fe28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564818"
---
# <a name="compiler-error-c2482"></a>Ошибка компилятора C2482

>"*идентификатор*": динамическая инициализация данных «thread» не допускается в WinRT или управляемого кода

## <a name="remarks"></a>Примечания

В управляемом или code WinRT, переменные, объявленные с помощью [__declspec(thread)](../../cpp/thread.md) атрибута модификатор класса хранилища или [thread_local](../../cpp/storage-classes-cpp.md#thread_local) спецификатор класса хранения не может инициализироваться с помощью выражения для этого требуется вычисление во время выполнения. Статическое выражение необходим для инициализации `__declspec(thread)` или `thread_local` данные в эти среды выполнения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2482 в управляемых (**/CLR**) и WinRT (**/ZW**) код:

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Чтобы устранить эту проблему, инициализировать локальное хранилище потока с помощью константы, **constexpr**, или статическое выражение. Выполните инициализацию конкретного потока по отдельности.