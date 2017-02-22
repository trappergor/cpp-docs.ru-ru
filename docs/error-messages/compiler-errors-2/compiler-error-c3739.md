---
title: "Ошибка компилятора C3739 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3739"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3739"
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3739
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": поддержка синтаксиса только в том случае, если параметр "layout\_dependent" для event\_receiver возвращает true  
  
 Произведена попытка подключения всего интерфейса событий, однако параметр `layout_dependent` для атрибута [event\_receiver](../../windows/event-receiver.md) имеет значение, отличное от true. Необходимо подключать события по одному.  
  
 Следующий пример приводит к возникновению ошибки C3739:  
  
```  
// C3739.cpp  
struct A  
{  
   __event void e();  
};  
  
// event_receiver is implied  
// [ event_receiver(layout_dependent=false)]  
  
// use the following line instead  
// [event_receiver(com, layout_dependent=true), coclass ]  
struct B  
{  
   void f();  
   B(A* a)  
   {  
      __hook(A, a, &B::f);   // C3739  
      // use the following line instead to hook a single event  
      // __hook(&A::e, a, &B::f);  
   }  
};  
  
int main()  
{  
}  
```