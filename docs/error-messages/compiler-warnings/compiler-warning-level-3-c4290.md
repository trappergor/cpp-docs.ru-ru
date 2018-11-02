---
title: Предупреждение компилятора (уровень 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: c585294686298a1197d437d41a0d541f1268985f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512740"
---
# <a name="compiler-warning-level-3-c4290"></a>Предупреждение компилятора (уровень 3) C4290

Спецификация исключений C++ игнорируется за исключением того, что функция не является __declspec(nothrow)

Функция объявляется с помощью спецификации исключений, которые принимает Visual C++, но не реализует. Создавайте код с исключением, которые могут потребоваться спецификации, которые учитываются во время компиляции, перекомпиляции и ссылку для его использования в будущих версиях, поддерживающих спецификации исключений.

Дополнительные сведения см. в разделе [спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md) .

Это предупреждение можно избежать, используя [предупреждение](../../preprocessor/warning.md) директивы pragma:

```
#pragma warning( disable : 4290 )
```

В следующем примере кода возникает C4290:

```
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```