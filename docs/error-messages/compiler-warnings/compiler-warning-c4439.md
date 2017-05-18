---
title: "Предупреждение компилятора C4439 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4439
dev_langs:
- C++
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b827d0d2feac4cafe4a90d58003a348ece36bd2d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4439"></a>Предупреждение компилятора C4439
«функция»: определение функции с управляемым типом в сигнатуре должно иметь соглашение о вызове __clrcall  
  
 Компилятор неявно заменяет соглашение о вызовах с [__clrcall](../../cpp/clrcall.md). Чтобы устранить это предупреждение, удалите `__cdecl` или `__stdcall` соглашение о вызовах.  
  
 C4439 всегда выводится в качестве ошибки. Можно отключить это предупреждение с `#pragma warning` или **/wd**; см. [предупреждение](../../preprocessor/warning.md) или [/w помощью/W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, /wd, и мы /wo, /Wv /WX (уровень предупреждения)](../../build/reference/compiler-option-warning-level.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4439.  
  
```  
// C4439.cpp  
// compile with: /clr  
void __stdcall f( System::String^ arg ) {}   // C4439  
void __clrcall f2( System::String^ arg ) {}   // OK  
void f3( System::String^ arg ) {}   // OK  
```
