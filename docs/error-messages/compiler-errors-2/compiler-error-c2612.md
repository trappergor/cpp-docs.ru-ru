---
title: Ошибка компилятора C2612
ms.date: 11/04/2016
f1_keywords:
- C2612
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
ms.openlocfilehash: 630e5b1cc6e99ffda28f50c09bccbbc2fea07172
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737703"
---
# <a name="compiler-error-c2612"></a>Ошибка компилятора C2612

Недопустимый замыкающий символ "char" в списке инициализаторов Base или Member

Символ появляется после последней базовой или члена в списке инициализаторов.

Следующий пример приводит к возникновению ошибки C2612:

```cpp
// C2612.cpp
class A {
public:
   int i;
   A( int ia ) : i( ia ) + {};   // C2612
};
```
