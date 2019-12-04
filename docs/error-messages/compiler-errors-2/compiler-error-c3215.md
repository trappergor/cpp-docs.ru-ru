---
title: Ошибка компилятора C3215
ms.date: 11/04/2016
f1_keywords:
- C3215
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
ms.openlocfilehash: 59d9eb0c28269e95b906042126cc3a9f25bba635
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751915"
---
# <a name="compiler-error-c3215"></a>Ошибка компилятора C3215

"тип1": универсальный параметр типа с уже имеющимся ограничением "тип2"

Ограничение указано более одного раза.

Дополнительные сведения об универсальных классах см. в разделе [Generics](../../extensions/generics-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3215:

```cpp
// C3215.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A,A
ref class C {};   // C3215
```

Возможное решение

```cpp
// C3215b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```
