---
title: Ошибка компилятора C3743 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3743
dev_langs:
- C++
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc9a0bab67bb4fb15627dde42b1d538a0ecce9d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266520"
---
# <a name="compiler-error-c3743"></a>Ошибка компилятора C3743
можно только обработчик или отсоединения весь интерфейс, когда параметр «layout_dependent» для event_receiver имеет значение true  
  
 [__Unhook](../../cpp/unhook.md) функция меняется в число параметров, принимаемых на значение, передаваемое `layout_dependent` параметр в [event_receiver](../../windows/event-receiver.md) класса.  
  
 Следующий пример приводит к возникновению ошибки C3743:  
  
```  
// C3743.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
[object] __interface I { HRESULT f(); };  
  
[event_receiver(com, layout_dependent=true), coclass]  
struct R : I {  
        HRESULT f() {  
      return 0;  
   }  
        R() {  
   }  
  
   R(I* a) {  
      __hook(I, a, &R::f);   // C3743  
      // The following line resolves the error.  
      // __hook(I, a);  
   }  
};  
```