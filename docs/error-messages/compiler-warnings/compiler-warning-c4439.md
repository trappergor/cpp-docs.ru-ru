---
title: Предупреждение компилятора C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: d604c234b9445a7e5304118124620f0057f30975
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311349"
---
# <a name="compiler-warning-c4439"></a>Предупреждение компилятора C4439

«функция»: определение функции с управляемым типом в сигнатуре должно иметь соглашение вызова __clrcall

Компилятор неявно заменяет соглашение о вызовах с [__clrcall](../../cpp/clrcall.md). Чтобы устранить это предупреждение, удалите `__cdecl` или `__stdcall` соглашение о вызовах.

C4439 всегда выдается как ошибка. Вы можете отключить это предупреждение с помощью `#pragma warning` или **/wd**; см. в разделе [предупреждение](../../preprocessor/warning.md) или [/w, / W0, / W1, / w2, / w3, / W4, / W1, / w2, / w3, / W4, / Wall, / WD, / we, / WO, / wv, /WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md)Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4439.

```
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```