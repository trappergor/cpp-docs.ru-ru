---
title: Ошибка компилятора C2637
ms.date: 11/04/2016
f1_keywords:
- C2637
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
ms.openlocfilehash: 4231a811911fdf600b47962e929f6f3cff1f1bca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395460"
---
# <a name="compiler-error-c2637"></a>Ошибка компилятора C2637

«Идентификатор»: невозможно изменить указатели на данные-члены

Указатель на данные-член не может иметь соглашение о вызовах. Чтобы устранить проблему, удалите соглашение о вызовах или объявить указатель на функцию-член.

Следующий пример приводит к возникновению ошибки C2637:

```
// C2637.cpp
// compile with: /c
struct S {};
int __stdcall S::*pms1;   // C2637

// OK
int S::*pms2;
int (__stdcall S::*pms3)(...);
```