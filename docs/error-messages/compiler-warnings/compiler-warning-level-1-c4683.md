---
title: Предупреждение (уровень 1) C4683 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 418bf25d565c616d5bc4aaf58361c4f28df298ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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