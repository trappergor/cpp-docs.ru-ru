---
title: Ошибка компилятора C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: 447869b029df41219f71dcc633e9ae8a3934e0ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549582"
---
# <a name="compiler-error-c2570"></a>Ошибка компилятора C2570

«Идентификатор»: объединение не может иметь базовые классы

Объединение является производным от класса, структуры или объединения. Это не допускается. Объявите производный тип как класс или структуру.

Следующий пример приводит к возникновению ошибки C2570:

```
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```