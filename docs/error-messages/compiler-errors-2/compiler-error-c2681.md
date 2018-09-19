---
title: Ошибка компилятора C2681 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2681
dev_langs:
- C++
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a0f0ab4b9c6a2dd2ae69f0370f808e32e496b97
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059086"
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