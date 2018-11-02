---
title: Ошибка компилятора C2755
ms.date: 11/04/2016
f1_keywords:
- C2755
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
ms.openlocfilehash: c2238058dc4b7df6bbe33e98d6ccde996f36b782
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570694"
---
# <a name="compiler-error-c2755"></a>Ошибка компилятора C2755

«параметр»: параметр частичной специализации не являющегося типом должен быть простым идентификатором

Параметр не являющегося типом должен быть простым идентификатором, то, что компилятор может разрешить во время компиляции один идентификатор или значение константы.

Следующий пример приводит к возникновению ошибки C2755:

```
// C2755.cpp
template<int I, int J>
struct A {};

template<int I>
struct A<I,I*5> {};   // C2755
// try the following line instead
// struct A<I,5> {};
```