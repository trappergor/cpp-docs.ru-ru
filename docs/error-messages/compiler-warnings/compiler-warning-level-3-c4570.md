---
title: Предупреждение компилятора (уровень 3) C4570
ms.date: 11/04/2016
f1_keywords:
- C4570
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
ms.openlocfilehash: 386d7c210c77469d67a75d66f7d8ae35c105b3b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401791"
---
# <a name="compiler-warning-level-3-c4570"></a>Предупреждение компилятора (уровень 3) C4570

«Тип»: не был объявлен явно как абстрактный, однако содержит абстрактные функции

Тип, содержащий [абстрактный](../../extensions/abstract-cpp-component-extensions.md) функции должен быть помечен как абстрактный.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4570.

```
// C4570.cpp
// compile with: /clr /W3 /c
ref struct X {   // C4570
// try the following line instead
// ref class X abstract {
   virtual void f() abstract;
};
```