---
title: Ошибка компилятора C2633
ms.date: 11/04/2016
f1_keywords:
- C2633
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
ms.openlocfilehash: 746f01706c7c0ec09a64c5faee748f9582ac9a14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662570"
---
# <a name="compiler-error-c2633"></a>Ошибка компилятора C2633

«Идентификатор»: «inline» является единственным допустимым классом хранения для конструкторов

Конструктор объявлен как класс хранения, отличные от встроенной.

Следующий пример приводит к возникновению ошибки C2633:

```
// C2633.cpp
// compile with: /c
class C {
   extern C();   // C2633, not inline
   inline C();   // OK
};
```