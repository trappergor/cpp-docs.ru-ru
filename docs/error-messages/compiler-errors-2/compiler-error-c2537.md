---
title: Ошибка компилятора C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 437727b334087aef496dbb0a1f3f1c8cf2b45458
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345588"
---
# <a name="compiler-error-c2537"></a>Ошибка компилятора C2537

«спецификатор»: Недопустимая спецификация компоновки

Возможные причины:

1. Описатель компоновки не поддерживается. Поддерживается только описатель компоновки «C».

1. Для более одной функции в наборе перегруженных функций указана компоновка «C». Это не допускается.

Следующий пример приводит к возникновению ошибки C2537:

```
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```