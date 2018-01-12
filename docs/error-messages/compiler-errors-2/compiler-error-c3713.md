---
title: "Ошибка компилятора C3713 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3713
dev_langs: C++
helpviewer_keywords: C3713
ms.assetid: 75c6b9b6-955b-49bd-9bc8-ced88b496a1f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da0ff1089166974830c12a588d85d6c09f068814
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3713"></a>Ошибка компилятора C3713
«метод»: метод обработчика событий должен возвращать такие же параметры функции, как и исходный «метод»  
  
 Можно определить метод обработчика событий, которая не использует те же параметры как исходный метод события. Чтобы устранить эту ошибку, предоставьте метод обработчика событий те же параметры, что и исходный метод события.  
  
 Следующий пример приводит к возникновению ошибки C3713:  
  
```  
// C3713.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1(int nValue);  
   // try the following line instead  
   // __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3713  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3713  
   }  
};  
```