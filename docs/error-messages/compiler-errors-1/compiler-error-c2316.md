---
title: "Ошибка компилятора C2316 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2316"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2316"
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2316
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"исключение": не может быть перехвачено, поскольку деструктор и \(или\) конструктор копии недоступны  
  
 Исключение было перехвачено значением или ссылкой, но конструктор копии и оператор назначения были недоступны.  
  
 Этот код был принят компилятором предыдущей версии, но теперь он приводит к ошибке.  
  
## Пример  
 При компиляции следующего примера возникнет ошибка C2316:  
  
```  
// C2316.cpp // compile with: /EHsc #include <stdio.h> extern "C" int printf_s(const char*, ...); struct B { public: B() {} // Delete the following line to resolve. private: // copy constructor B(const B&) { } }; void f(const B&) { } int main() { try { B aB; f(aB); } catch (B b) {   // C2316 printf_s("Caught an exception!\n"); } }  
```