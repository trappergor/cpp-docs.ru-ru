---
title: Ошибка компилятора C2612
ms.date: 11/04/2016
f1_keywords:
- C2612
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
ms.openlocfilehash: b2d4888c1be39c4f48f0ca674426c7af612b9bb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379029"
---
# <a name="compiler-error-c2612"></a>Ошибка компилятора C2612

в конце «char» недопустим в списке инициализаторов базового класса или члена

Символ отображается после последнего базового класса или члена в списке инициализаторов.

Следующий пример приводит к возникновению ошибки C2612:

```
// C2612.cpp
class A {
public:
   int i;
   A( int ia ) : i( ia ) + {};   // C2612
};
```