---
title: Ошибка компилятора C2523
ms.date: 11/04/2016
f1_keywords:
- C2523
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
ms.openlocfilehash: 56b0f88949d7a7fa5af945ab5d03ee9a480d6d3f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746426"
---
# <a name="compiler-error-c2523"></a>Ошибка компилятора C2523

"класс:: ~ идентификатор": несоответствие тегов деструктора или метода завершения

Имя деструктора должно быть именем класса, которому предшествует тильда (`~`). Конструктор и деструктор являются единственными членами, которые имеют то же имя, что и класс.

Следующий пример приводит к возникновению ошибки C2523:

```cpp
// C2523.cpp
// compile with: /c
class A {
   ~B();    // C2523
   ~A();   // OK
};
```
