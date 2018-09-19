---
title: Ошибка компилятора C2803 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7885735ebad1ff90afaf4ba8eaf6dfca9f3e0ab3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027045"
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