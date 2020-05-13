---
title: Предупреждение компилятора (уровень 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: 5970aa439a450bda4c1a2036da299d5c3cfbdb7a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198904"
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
