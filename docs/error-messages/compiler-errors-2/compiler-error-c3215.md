---
title: Ошибка компилятора C3215
ms.date: 11/04/2016
f1_keywords:
- C3215
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
ms.openlocfilehash: 24f17d2990c9258168a6d37fef101c21f62cb08d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768657"
---
# <a name="compiler-error-c3215"></a>Ошибка компилятора C3215

"тип1": универсальный параметр типа с уже имеющимся ограничением "тип2"

Ограничение указано более одного раза.

Дополнительные сведения об универсальных классах см. в разделе [Generics](../../extensions/generics-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3215:

```
// C3215.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A,A
ref class C {};   // C3215
```

Возможное решение

```
// C3215b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```