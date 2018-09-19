---
title: Ошибка компилятора C2711 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2711
dev_langs:
- C++
helpviewer_keywords:
- C2711
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5a2e757c525d272055077cb95516abf42c06dbc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088440"
---
# <a name="compiler-error-c2711"></a>Ошибка компилятора C2711

«функция»: эту функцию невозможно скомпилировать как управляемую, рассмотрите возможность с помощью #pragma неуправляемые

Некоторые инструкции будет запретить компилятору Создание MSIL для включающей функции.

Следующий пример приводит к возникновению ошибки C2711:

```
// C2711.cpp
// compile with: /clr
// processor: x86
using namespace System;
value struct V {
   static const t = 10;
};

void bar() {
   V::t;
   __asm int 3   // C2711 inline asm can't be compiled managed
}
```