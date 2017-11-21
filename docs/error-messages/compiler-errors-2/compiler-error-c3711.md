---
title: "Ошибка компилятора C3711 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3711
dev_langs: C++
helpviewer_keywords: C3711
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0cfc4a2ffbbf65f1a1171a256ce08d5f498887a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3711"></a>Ошибка компилятора C3711
«метод»: исходный метод неуправляемого событий должен возвращать тип void или целочисленный тип  
  
 Метод определен в источник события, который не возвращает значение void или целочисленный тип. Чтобы устранить эту ошибку, измените событие и обработчик событий, которые имеют тип возвращаемого значения `void` или целочисленный тип, такой как `int` или `long`.  
  
 Следующий пример приводит к возникновению ошибки C3711:  
  
```  
// C3711.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[event_source(native)]  
class CEventSrc {  
public:  
   __event float event1();   // C3711  
   // try the following line instead  
   // __event int event1();  
   // also change the handler, below  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   float handler1() {         // change float to int  
      return 0.0;             // change 0.0 to 0  
   }  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
};  
  
int main() {  
}  
```