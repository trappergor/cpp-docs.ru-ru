---
title: Ошибка компилятора C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: 9c9772052b690ad87de1d408c06478d82d48e724
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282118"
---
# <a name="compiler-error-c2652"></a>Ошибка компилятора C2652

«Идентификатор»: недопустимый конструктор копий: первый параметр не должен быть «идентификатор»

Первый параметр в конструктор копии имеет тот же тип как класса, структуры или объединения, для которого она определена. Первый параметр может быть ссылкой на тип, но не сам тип.

Следующий пример приводит к возникновению ошибки C2651:

```
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```