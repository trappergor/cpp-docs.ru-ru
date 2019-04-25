---
title: Ошибка компилятора C3239
ms.date: 11/04/2016
f1_keywords:
- C3239
helpviewer_keywords:
- C3239
ms.assetid: 22a518b7-020f-4f3c-9963-a094667fd1ac
ms.openlocfilehash: ec5a1e3a968c9342ba6d386ef1e2be133e45b62c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174046"
---
# <a name="compiler-error-c3239"></a>Ошибка компилятора C3239

"тип": указатель на внутреннюю часть или точечный указатель запрещается средой CLR

Компилятор обнаружил недопустимый тип.

В следующем примере возникает ошибка C3229.

```
// C3239.cpp
// compile with: /clr
int main() {
   interior_ptr<int>* pip0;   // C3239

   // OK
   int * pip1;
   interior_ptr<int> pip2;
   int ** pip;
}
```