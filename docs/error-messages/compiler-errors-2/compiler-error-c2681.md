---
title: Ошибка компилятора C2681
ms.date: 11/04/2016
f1_keywords:
- C2681
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
ms.openlocfilehash: 8b311052d3a3525090d954c0dc8cee20e985b1b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282144"
---
# <a name="compiler-error-c2681"></a>Ошибка компилятора C2681

«Тип»: недопустимый тип выражения для имени

Оператор приведения предпринял попытку преобразования из недопустимого типа. Например, если вы используете [dynamic_cast](../../cpp/dynamic-cast-operator.md) оператор преобразования выражения в тип указателя, исходное выражение должно быть указателем.

Следующий пример приводит к возникновению ошибки C2681:

```
// C2681.cpp
class A { virtual void f(); };

void g(int i) {
    A* pa;
    pa = dynamic_cast<A*>(i);  // C2681
}
```