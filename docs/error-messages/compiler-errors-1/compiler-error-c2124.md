---
title: Ошибка компилятора C2124
ms.date: 11/04/2016
f1_keywords:
- C2124
helpviewer_keywords:
- C2124
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
ms.openlocfilehash: 82bc4447aaf27190c013edf48a20a56c57a646c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397657"
---
# <a name="compiler-error-c2124"></a>Ошибка компилятора C2124

деление на ноль или остаток от деления на ноль

Константное выражение имеет в знаменателе ноль. Чтобы устранить эту ошибку, следует исключить деление на ноль.

В следующем примере возникает ошибка C2124:

```
// C2124.cpp
int main() {
  int i = 1 / 0;   // C2124  do not divide by zero
  int i2 = 12 / 2;   // OK
}
```