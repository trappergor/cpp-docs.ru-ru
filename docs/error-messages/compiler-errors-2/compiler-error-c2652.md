---
title: Ошибка компилятора C2652 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37b7b259b8eb42692641883c8d69578542cce06e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076623"
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