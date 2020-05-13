---
title: Предупреждение компилятора C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: c125fa84119c62e3090611c9a841f46eee759711
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165214"
---
# <a name="compiler-warning-c4439"></a>Предупреждение компилятора C4439

"функция": определение функции с управляемым типом в сигнатуре должно иметь __clrcallное соглашение о вызовах

Компилятор неявно заменяет соглашение о вызовах на [__clrcall](../../cpp/clrcall.md). Чтобы устранить это предупреждение, удалите соглашение о вызовах `__cdecl` или `__stdcall`.

C4439 всегда выдается как ошибка. Это предупреждение можно отключить с помощью `#pragma warning` или **/WD**; Дополнительные сведения см. в разделе [warning](../../preprocessor/warning.md) или [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/WD,/We,/WO,/WV,/WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4439.

```cpp
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```
