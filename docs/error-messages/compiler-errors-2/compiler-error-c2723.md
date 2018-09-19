---
title: Ошибка компилятора C2723 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2723
dev_langs:
- C++
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b1be2d81ecec7eb96fd9c1cd7e9938ce509f71e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072021"
---
# <a name="compiler-error-c2723"></a>Ошибка компилятора C2723

function: недопустимый описатель specifier в определении функции

Описатель не может использоваться в определении функции вне объявления класса. Описатель `virtual` может быть указан только в объявлении функции-члена внутри объявления класса.

В следующем примере показано возникновение ошибки C2723 и приводятся сведения по ее устранению.

```
// C2723.cpp
struct X {
   virtual void f();
   virtual void g();
};

virtual void X::f() {}   // C2723

// try the following line instead
void X::g() {}
```