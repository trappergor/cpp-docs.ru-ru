---
title: Ошибка компилятора C3717 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3717
dev_langs:
- C++
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efe6cdb53b3ee78016c25b273eb4682ec380d12f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3717"></a>Ошибка компилятора C3717
«метод»: метод, порождающий события не может быть определен  
  
 Был объявлен метод событий, который включает в себя реализацию. [__Event](../../cpp/event.md) объявление метода не может иметь определение. Чтобы устранить эту ошибку, убедитесь, что объявления методов событий не имеют определений. Например, в следующем коде удалить тело функции из `event1` объявления, как указано в комментариях.  
  
 Следующий пример приводит к возникновению ошибки C3717:  
  
```  
// C3717.cpp  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1() {   // C3717  
   }  
  
   // remove definition for event1 and substitute following declaration  
   // __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {  
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