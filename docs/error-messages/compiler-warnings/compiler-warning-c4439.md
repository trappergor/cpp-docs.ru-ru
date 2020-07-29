---
title: Предупреждение компилятора C4439
ms.date: 11/04/2016
f1_keywords:
- C4439
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
ms.openlocfilehash: baf74733c94fdb03f130d2300d0918845cc4de4c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223334"
---
# <a name="compiler-warning-c4439"></a>Предупреждение компилятора C4439

"функция": определение функции с управляемым типом в сигнатуре должно иметь __clrcallное соглашение о вызовах

Компилятор неявно заменяет соглашение о вызовах на [`__clrcall`](../../cpp/clrcall.md) . Чтобы устранить это предупреждение, удалите **`__cdecl`** **`__stdcall`** соглашение о вызовах или.

C4439 всегда выдается как ошибка. Это предупреждение можно отключить с помощью `#pragma warning` или **`/wd`** ; см. [предупреждение](../../preprocessor/warning.md) или [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/WD,/We,/WO,/WV,/WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md) для получения дополнительных сведений.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4439.

```cpp
// C4439.cpp
// compile with: /clr
void __stdcall f( System::String^ arg ) {}   // C4439
void __clrcall f2( System::String^ arg ) {}   // OK
void f3( System::String^ arg ) {}   // OK
```
