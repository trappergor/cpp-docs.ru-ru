---
title: "Ошибка компилятора C2811 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2811"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2811"
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2811
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип 1": не удается наследовать от "типа 2", ссылочный класс может наследовать только от ссылочного класса или класса интерфейса  
  
 Попытка использовать неуправляемый класс в качестве базового класса для управляемого класса.  
  
 Следующий пример приводит к возникновению ошибки C2811:  
  
```  
// C2811.cpp  
// compile with: /clr /c  
struct S{};  
ref struct T {};  
ref class C : public S {};   // C2811  
ref class D : public T {};   // OK  
```