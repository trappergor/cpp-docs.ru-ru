---
title: "Предупреждение компилятора (уровень 1) C4683 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4683"
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

***функция* : у источника события имеется параметр "out"; установка нескольких обработчиков событий должна проводиться с осторожностью**  
  
 Если несколько приемников события ожидает источника события COM, значение выходного параметра может игнорироваться.  
  
 Следует помнить, что в следующих случаях происходит утечка памяти.  
  
1.  Если в методе есть выходной параметр, память для которого выделяется внутри него, например, BSTR \*.  
  
2.  Если у события несколько обработчиков \(это групповое событие\).  
  
 Причина утечки заключается в том, что выходной параметр задается несколькими обработчиками, но при этом возвращается в точку вызова только последним из них.  
  
 Следующий пример приводит к возникновению ошибки C4683:  
  
```  
// C4683.cpp  
// compile with: /W1 /LD  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="xx") ];  
  
[ object ]  
__interface I {  
   HRESULT f([out] int* pi);  
   // try the following line instead  
   // HRESULT f(int* pi);  
};  
  
[ coclass, event_source(com) ]  
struct E {  
   __event __interface I;   // C4683  
};  
```