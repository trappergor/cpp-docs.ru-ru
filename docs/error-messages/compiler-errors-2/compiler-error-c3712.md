---
title: "Ошибка компилятора C3712 | Microsoft Docs"
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
  - "C3712"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3712"
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3712
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"метод": метод обработчика событий должен возвращать такой же тип, как и исходный "метод"  
  
 Определен метод обработчика событий, который не возвращал тот же тип, как и исходный метод события.  Чтобы устранить ошибку, следует предоставить обработчику событий тот же тип возвращаемого события, который был предоставлен исходному методу события.  
  
 Следующий пример приводит к возникновению ошибки C3712:  
  
```  
// C3712.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   int handler1() { return 0; }  
   // try the following line instead  
   // void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712  
   }  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712  
   }  
};  
```