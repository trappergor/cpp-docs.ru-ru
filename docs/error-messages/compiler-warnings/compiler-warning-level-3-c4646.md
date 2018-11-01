---
title: Предупреждение компилятора (уровень 3) C4646
ms.date: 11/04/2016
f1_keywords:
- C4646
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
ms.openlocfilehash: 03ea8328351a594e04988e3544686d8c5dc1144a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638767"
---
# <a name="compiler-warning-level-3-c4646"></a>Предупреждение компилятора (уровень 3) C4646

функция, объявленная с атрибутом __declspec(noreturn) имеет тип, отличный от void

Функция, помеченная модификатором [noreturn](../../cpp/noreturn.md) `__declspec` , должна иметь тип возврата [void](../../cpp/void-cpp.md) .

В следующем примере возникает ошибка C4646.

```
// C4646.cpp
// compile with: /W3 /WX
int __declspec(noreturn) TestFunction()
{   // C4646  make return type void
}
```