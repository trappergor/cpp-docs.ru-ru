---
title: Ошибка компилятора C2482 | Документы Microsoft
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2482
dev_langs:
- C++
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3dd23069f389d0a02e10d26edb7ee4fd3c373cb
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="compiler-error-c2482"></a>Ошибка компилятора C2482

>"*идентификатор*": динамическая инициализация данных «thread» не допускается в коде managed WinRT

## <a name="remarks"></a>Примечания

При использовании управляемых или code WinRT, переменные, объявленные с помощью [__declspec(thread)](../../cpp/thread.md) атрибута модификатор класса хранения или [thread_local](../../cpp/storage-classes-cpp.md#thread_local) спецификатор класса хранения не может инициализироваться с помощью выражения для этого требуется вычисление во время выполнения. Статическое выражение, необходимые для инициализации `__declspec(thread)` или `thread_local` данные в этих средах выполнения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2482 в управляемых (**/CLR**) и WinRT (**/zw**) кода:

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Чтобы устранить эту проблему, инициализировать локальное хранилище потока с помощью константы, **constexpr**, или статическое выражение. Выполните инициализацию потоках отдельно.