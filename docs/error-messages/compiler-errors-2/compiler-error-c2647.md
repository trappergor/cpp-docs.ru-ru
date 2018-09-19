---
title: Ошибка компилятора C2647 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2647
dev_langs:
- C++
helpviewer_keywords:
- C2647
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14187f7b74096a3a863798053ab260177d2f378b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045891"
---
# <a name="compiler-error-c2647"></a>Ошибка компилятора C2647

«operator»: Невозможно разыменовать «тип1» в «тип2»

Левый операнд оператора указателя на член ( `->*` или `.*` ) не может неявно преобразовать в тип, относящийся к правому оператору.

Следующий пример приводит к возникновению ошибки C2647:

```
// C2647.cpp
class C {};
class D {};

int main() {
   D d, *pd;
   C c, *pc = 0;
   int C::*pmc = 0;
   pd->*pmc = 0;   // C2647
   d.*pmc = 0;   // C2647

   // OK
   pc->*pmc = 0;
   c.*pmc = 0;
}
```