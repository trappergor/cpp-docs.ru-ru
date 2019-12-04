---
title: Ошибка компилятора C2930
ms.date: 11/04/2016
f1_keywords:
- C2930
helpviewer_keywords:
- C2930
ms.assetid: f07eecd1-e5d1-4518-bd89-b1fd2a003a17
ms.openlocfilehash: b30e614236298cf9a07cbc29e028039903f9748f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760984"
---
# <a name="compiler-error-c2930"></a>Ошибка компилятора C2930

"класс": идентификатор типа класса переопределен как перечислитель "идентификатор_перечисления"

Универсальный класс или класс шаблона нельзя использовать в качестве члена перечисления.

Эта ошибка может возникнуть при неправильной расстановке скобок.

В следующем примере возникает ошибка C2930:

```cpp
// C2930.cpp
// compile with: /c
template<class T>
class x{};
enum SomeEnum { x };   // C2930

class y{};
enum SomeEnum { y };
```

Ошибка C2930 также может возникнуть при использовании универсальных шаблонов:

```cpp
// C2930c.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
enum SomeEnum { GC };   // C2930

ref struct GC2 {};
enum SomeEnum2 { GC2 };
```
