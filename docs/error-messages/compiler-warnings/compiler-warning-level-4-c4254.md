---
title: Предупреждение компилятора (уровень 4) C4254
ms.date: 11/04/2016
f1_keywords:
- c4254
helpviewer_keywords:
- C4254
ms.assetid: c7dcef24-d535-4c98-bb41-fc3d2b88fd11
ms.openlocfilehash: 925428cffae37ea26144e5b550cbc7988b33ef01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606411"
---
# <a name="compiler-warning-level-4-c4254"></a>Предупреждение компилятора (уровень 4) C4254

«operator»: преобразование из «тип1» в «тип2», возможна потеря данных

Крупное битовое поле было назначено меньшего размера битовое поле. Возможна потеря данных.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4254:

```
// C4254.cpp
// compile with: /W4
#pragma warning(default: 4254)

struct X {
   int a : 20;
   int b : 12;
};

int main() {
   X *x = new X();
   x->b = 10;
   x->a = 4;
   x->a = x->b;    // OK
   x->b = x->a;    // C4254
};
```