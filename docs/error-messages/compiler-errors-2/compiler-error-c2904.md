---
title: Ошибка компилятора C2904
ms.date: 11/04/2016
f1_keywords:
- C2904
helpviewer_keywords:
- C2904
ms.assetid: d5802f2e-d3fc-473d-aa04-36957b4eaca5
ms.openlocfilehash: 90e0ae54e9d3c218040cfa8665f742be92ad7487
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641526"
---
# <a name="compiler-error-c2904"></a>Ошибка компилятора C2904

"идентификатор": имя уже использовано для шаблона в текущей области видимости

Проверьте наличие повторяющихся имен в коде.

Следующий пример приводит к возникновению ошибки C2904:

```
// C2904.cpp
// compile with: /c
void X();  // X is declared as a function
template<class T> class X{};  // C2904
```