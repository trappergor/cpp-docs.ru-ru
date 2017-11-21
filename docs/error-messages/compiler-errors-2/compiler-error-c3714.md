---
title: "Ошибка компилятора C3714 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3714
dev_langs: C++
helpviewer_keywords: C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7d58e06d99975fd4ccff9ea4bace755ff1d758cb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3714"></a>Ошибка компилятора C3714
«метод»: метод обработчика событий должен возвращать соглашение о вызове, как и исходный «метод»  
  
 Можно определить метод обработчика событий, в котором не используется соглашение о вызове как исходный метод события. Чтобы устранить эту ошибку, предоставьте метод обработчика событий же соглашения о вызове как и исходный метод события. Например, в следующем коде создать соглашение о вызовах `handler1` и `event1` совпадают ([__cdecl](../../cpp/cdecl.md) или [__stdcall](../../cpp/stdcall.md) или другие). Удаление вызов ключевые слова соглашения о из обоих объявлений приведет также решить проблему и вызвать `event1` и `handler1` для использования по умолчанию [thiscall](../../cpp/thiscall.md) соглашение о вызовах. В разделе [соглашения о вызовах](../../cpp/calling-conventions.md) для получения дополнительной информации.  
  
 Следующий пример приводит к возникновению ошибки C3714:  
  
```  
// C3714.cpp  
// compile with: /c  
// processor: x86  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void __cdecl event1();  
   // try the following line instead  
   // __event void __stdcall event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void __stdcall handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714  
   }  
};  
```