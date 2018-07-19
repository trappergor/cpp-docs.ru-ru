---
title: Предупреждение компилятора C4439 | Документы Microsoft
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
ms.openlocfilehash: 4767f03d51bf1fcaac51678d17d454949eb30875
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286959"
---
# <a name="compiler-warning-c4439"></a>Предупреждение компилятора C4439
«функция»: определение функции с управляемым типом в сигнатуре должно иметь соглашение вызова __clrcall  
  
 Компилятор неявно заменяет соглашение о вызовах с [__clrcall](../../cpp/clrcall.md). Чтобы устранить это предупреждение, удалите `__cdecl` или `__stdcall` соглашение о вызовах.  
  
 C4439 всегда выдается как ошибка. Можно отключить это предупреждение с `#pragma warning` или **/wd**; в разделе [предупреждение](../../preprocessor/warning.md) или  [ /w, помощью/W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, /wd, и мы /wo, / wv, / WX (порог предупреждений)](../../build/reference/compiler-option-warning-level.md)для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4439.  
  
```  
// C4439.cpp  
// compile with: /clr  
void __stdcall f( System::String^ arg ) {}   // C4439  
void __clrcall f2( System::String^ arg ) {}   // OK  
void f3( System::String^ arg ) {}   // OK  
```