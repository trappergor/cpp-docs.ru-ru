---
title: Ошибка компилятора C3886
ms.date: 11/04/2016
f1_keywords:
- C3886
helpviewer_keywords:
- C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
ms.openlocfilehash: e9e9d4b478d5b53e50203d1f009295e1da444f2d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402545"
---
# <a name="compiler-error-c3886"></a>Ошибка компилятора C3886

«var»: данные-член литерала должны инициализироваться

Объект [литерала](../../extensions/literal-cpp-component-extensions.md) переменная должна быть инициализирована при ее объявлении.

Следующий пример приводит к возникновению ошибки C3886:

```
// C3886.cpp
// compile with: /clr /c
ref struct Y1 {
   literal int staticConst;   // C3886
   literal int staticConst2 = 0;   // OK
};
```