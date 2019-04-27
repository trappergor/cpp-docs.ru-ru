---
title: Ошибка компилятора C2762
ms.date: 11/04/2016
f1_keywords:
- C2762
helpviewer_keywords:
- C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
ms.openlocfilehash: 0cb05d0e111319ff135bdb48d51af6eb4a2f2353
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257547"
---
# <a name="compiler-error-c2762"></a>Ошибка компилятора C2762

«класс»: Недопустимое выражение в качестве аргумента шаблона для «аргумент»

При использовании [/Za](../../build/reference/za-ze-disable-language-extensions.md), компилятор не преобразует целочисленный указатель.

Следующий пример приводит к возникновению ошибки C2762:

```
// C2762.cpp
// compile with: /Za
template<typename T, T *pT>
class X2 {};

void f2() {
   X2<int, 0> x21;   // C2762
   // try the following line instead
   // X2<int, static_cast<int *>(0)> x22;
}
```