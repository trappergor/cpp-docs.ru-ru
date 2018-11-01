---
title: Ошибка компилятора C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: dcfac9629a90b82744f87ec105c30301b2102cdf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601478"
---
# <a name="compiler-error-c2062"></a>Ошибка компилятора C2062

Тип «тип» непредвиденный

Компилятор не ожидала имени типа.

Следующий пример приводит к возникновению ошибки C2062:

```
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062 также может возникать из-за способа компилятор обрабатывает неопределенные типы в списке параметров конструктора. Если компилятор обнаруживает неопределенный тип (с опечаткой?), предполагается конструктор — это выражение и выдает C2062. Чтобы решить, используйте только определенные типы в списке параметров конструктора.