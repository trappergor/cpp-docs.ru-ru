---
title: Предупреждение компилятора (уровень 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: 5ccacd7d5f4dfd2e9ad8de3958d7aa43571091fe
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051653"
---
# <a name="compiler-warning-level-3-c4290"></a>Предупреждение компилятора (уровень 3) C4290

C++спецификация исключения игнорируется, за исключением того, что функция не __declspec (throw)

Функция объявляется с помощью спецификации исключения, которая C++ поддерживает, но не реализует. Код с спецификациями исключений, которые игнорируются во время компиляции, может потребоваться перекомпилировать и связать с ними для повторного использования в будущих версиях, поддерживающих спецификации исключений.

Дополнительные сведения см. в разделе [спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md) .

Это предупреждение можно избежать с помощью директивы pragma [warning](../../preprocessor/warning.md) :

```cpp
#pragma warning( disable : 4290 )
```

Следующий пример кода приводит к возникновению ошибки C4290:

```cpp
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```