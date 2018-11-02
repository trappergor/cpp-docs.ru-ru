---
title: Ошибка компилятора C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: d20b8dde9f4134273adcba0f947f685f7ce7d213
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447272"
---
# <a name="compiler-error-c2803"></a>Ошибка компилятора C2803

«оператор» должен иметь по крайней мере один формальный параметр типа класса

Перегруженный оператор не имеет параметра типа класса.

Необходимо передать по крайней мере один параметр по ссылке (без использования указателей, но ссылки) или по значению, чтобы иметь возможность записи «< b» (тип класса A и b).

Если оба аргумента являются указателями, он будет простое сравнение адресов указателя и не будет использовать определенное пользователем преобразование.

Следующий пример приводит к возникновению ошибки C2803:

```
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```