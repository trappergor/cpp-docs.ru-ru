---
title: Предупреждение компилятора C4439 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4439
dev_langs:
- C++
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 646b057f3f25bec8b686b08d50f0e473542ddcfc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076116"
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