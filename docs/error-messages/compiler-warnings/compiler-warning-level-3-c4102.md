---
title: Предупреждение компилятора (уровень 3) C4102
ms.date: 11/04/2016
f1_keywords:
- C4102
helpviewer_keywords:
- C4102
ms.assetid: 349f308a-daf3-48c6-bd53-6c38b73f8880
ms.openlocfilehash: 9e5b4850c82083e19a0fe859b1021b5beecf1a1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402311"
---
# <a name="compiler-warning-level-3-c4102"></a>Предупреждение компилятора (уровень 3) C4102

"метка": неиспользованная метка

Метка определена, но нигде не используется. Компилятор пропускает метку.

Следующий пример приводит к возникновению предупреждения C4102:

```
// C4102.cpp
// compile with: /W3
int main() {
   int a;

   test:   // C4102, remove the unreferenced label to resolve

   a = 1;
}
```