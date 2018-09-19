---
title: Ошибка компилятора C2593 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2593
dev_langs:
- C++
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a3b0d1a8574aa5c05bbca023a1209cf1801f57e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042732"
---
# <a name="compiler-error-c2593"></a>Ошибка компилятора C2593

«Идентификатор оператор» является неоднозначным

Несколько возможных оператор определен для перегруженного оператора.

Чтобы устранить эту ошибку, используйте явное приведение на один или несколько фактических параметров.

Следующий пример приводит к возникновению ошибки C2593:

```
// C2593.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};
void operator+( X, X );
void operator+( A, B );
D d;

int main() {
   d +  d;         // C2593, D has an A, B, and X
   (X)d + (X)d;    // OK, uses operator+( X, X )
}
```

Эта ошибка может быть вызвана путем сериализации с плавающей запятой переменной с помощью `CArchive` объекта. Компилятор определяет `<<` оператор неопределенности. Единственными простыми типами C++, `CArchive` можно сериализовать типы фиксированного размера `BYTE`, `WORD`, `DWORD`, и `LONG`. Все целочисленные типы должен быть приведен к одному из этих типов для сериализации. Типы с плавающей запятой должны быть заархивированы с помощью `CArchive::Write()` функция-член.

В следующем примере показано, как архивировать переменную с плавающей запятой (`f`) для архива `ar`:

```
ar.Write(&f, sizeof( float ));
```