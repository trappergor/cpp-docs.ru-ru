---
title: Ошибка компилятора C2482
ms.date: 09/15/2017
f1_keywords:
- C2482
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
ms.openlocfilehash: 5afa81369b2cf329baae02bc1309587015946409
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205157"
---
# <a name="compiler-error-c2482"></a>Ошибка компилятора C2482

>"*идентификатор*": динамическая инициализация данных "Thread" не разрешена в коде управляемого кода или WinRT

## <a name="remarks"></a>Remarks

В управляемом коде или в среде WinRT переменные, объявленные с помощью атрибута класса хранения [__declspec (thread)](../../cpp/thread.md) или спецификатора класса хранения [thread_local](../../cpp/storage-classes-cpp.md#thread_local) , не могут быть инициализированы выражением, требующим вычисления во время выполнения. Для инициализации `__declspec(thread)` или `thread_local` данных в этих средах выполнения требуется статическое выражение.

## <a name="example"></a>Пример

В следующем примере создается C2482 в Managed ( **/CLR**) и в коде WinRT ( **/ZW**):

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Чтобы устранить эту проблему, инициализируйте локальное хранилище потока с помощью константы, **constexpr**или статического выражения. Выполните отдельную инициализацию для конкретного потока.
