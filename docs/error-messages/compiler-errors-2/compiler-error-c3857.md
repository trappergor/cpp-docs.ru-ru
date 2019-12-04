---
title: Ошибка компилятора C3857
ms.date: 11/04/2016
f1_keywords:
- C3857
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
ms.openlocfilehash: 2fe4973c3452e86449aec56c1f7cb40d5ea4a2cb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754814"
---
# <a name="compiler-error-c3857"></a>Ошибка компилятора C3857

"тип": несколько списков параметров типа не допускаются

Для одного и того же типа задано несколько шаблонов или универсальных типов, что недопустимо.

Следующий пример приводит к возникновению ошибки C3857:

```cpp
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

Возможное решение

```cpp
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

C3857 также может возникать при использовании универсальных шаблонов:

```cpp
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

Возможное решение

```cpp
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```
