---
title: "Ошибка компилятора C3665 | Microsoft Docs"
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
  - "C3665"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3665"
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3665
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"деструктор": спецификатор переопределения "ключевое слово" не допускается в деструкторе или методе завершения  
  
 В деструкторе или методе завершения используется недопустимое ключевое слово.  
  
 Например, в деструкторе или методе завершения не допускается запрос новой области памяти.  Дополнительные сведения см. в разделах [Явное переопределение](../../windows/explicit-overrides-cpp-component-extensions.md) и [Деструкторы и завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Следующий пример приводит к возникновению ошибки C3665:  
  
```  
// C3665.cpp  
// compile with: /clr  
public ref struct R {  
   virtual ~R() { }  
   virtual void a() { }  
};  
  
public ref struct S : R {  
   virtual ~S() new {}   // C3665  
   virtual void a() new {}   // OK  
};  
```