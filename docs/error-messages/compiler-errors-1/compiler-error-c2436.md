---
title: Ошибка компилятора C2436 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2436
dev_langs:
- C++
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f32b94f0e68de893897a5bdf48977a47417e6729
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032995"
---
# <a name="compiler-error-c2436"></a>Ошибка компилятора C2436

«Идентификатор»: функция-член или вложенный класс в списке инициализации конструктора

Не удается инициализировать функции-члены и локальные классы в списке инициализации конструктора.

Следующий пример приводит к возникновению ошибки C2436:

```
// C2436.cpp
struct S{
   int f();
   struct Inner{
      int i;
   };
   S():f(10), Inner(0){}   // C2436
};
```