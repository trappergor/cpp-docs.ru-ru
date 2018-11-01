---
title: Ошибка компилятора C3890
ms.date: 11/04/2016
f1_keywords:
- C3890
helpviewer_keywords:
- C3890
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
ms.openlocfilehash: 2354be5ac7299fc0361e1b3ad50554e9949f8c1d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599487"
---
# <a name="compiler-error-c3890"></a>Ошибка компилятора C3890

«var»: невозможно получить адрес данные-член литерала

Данные-член литерала существует в куче сбора мусора.  Можно перемещать объект в куче сбора мусора, поэтому получение адреса не используется.

Следующий пример приводит к возникновению ошибки C3890:

```
// C3890.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   int p = &Y1::staticConst;   // C3890
   int p2 = Y1::staticConst;   // OK
}
```