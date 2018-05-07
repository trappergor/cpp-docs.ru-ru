---
title: Предупреждение (уровень 1) C4925 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4925
dev_langs:
- C++
helpviewer_keywords:
- C4925
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 157b09aff38212e9257eb3557770dae57d04bf58
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4925"></a>Предупреждение компилятора (уровень 1) C4925
"метод": метод disp-интерфейса нельзя вызвать из скрипта  
  
 Скриптовые языки не могут создавать параметр in VT_BYREF; они могут создавать только параметры out VT_BYREF.  
  
 Другой способ устранения этого предупреждения — не присваивать параметру (в определении и реализации) тип указателя.  
  
 Следующий пример приводит к возникновению предупреждения C4925:  
  
```  
// C4925.cpp  
// compile with: /LD /W1  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[ module(name="Test")];  
  
[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IDisp {  
   [id(9)] void f([in] int*);  
};  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002")  ]  
struct CDisp : IDisp {   // C4925  
   void f(int*) {}  
};  
```