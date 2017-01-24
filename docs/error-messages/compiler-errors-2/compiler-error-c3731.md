---
title: "Ошибка компилятора C3731 | Microsoft Docs"
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
  - "C3731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3731"
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

несовместимое событие "функция 1" и обработчик "функция 2"; источник события и обработчик событий должны быть одного типа  
  
 Источник события и приемника событий должны иметь тот же тип \(например `native` и типов `com` \).  Чтобы исправить ошибку, сделайте одинаковыми типы источника и обработчика событий.  
  
 Следующий пример приводит к возникновению ошибки C3731:  
  
```  
// C3731.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
[event_source(native)]  
struct A {  
   __event void MyEvent();  
};  
  
[event_receiver(managed)]  
// try the following line instead  
// [event_receiver(native)]  
struct B {  
   void func();  
   B(A a) {  
      __hook(&A::MyEvent, &a, &B::func);   // C3731  
   }  
};  
  
int main() {  
}  
```