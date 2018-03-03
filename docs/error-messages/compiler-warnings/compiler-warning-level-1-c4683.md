---
title: "Предупреждение (уровень 1) C4683 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e0a8ca498a3c95a1b37229f6ac973cf74a8e28ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4683"></a>Предупреждение компилятора (уровень 1) C4683
**'**   
 ***функция* ": источник событий имеет «out»-параметра; соблюдайте осторожность при использовании нескольких обработчиков события**  
  
 Если более чем один приемник событий прослушивает для источника событий модели COM, могут игнорироваться значение выходного параметра.  
  
 Имейте в виду, что утечка памяти будут происходить в следующих случаях:  
  
1.  Если метод имеет выходной параметр, который выделяется внутри него, например BSTR *.  
  
2.  Если событие имеет несколько обработчиков (это групповое событие)  
  
 Причина утечки является параметр out будет задать более одного обработчиком, но возвращается к месту вызова последнего обработчиком.  
  
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