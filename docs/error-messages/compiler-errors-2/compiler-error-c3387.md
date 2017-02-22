---
title: "Compiler Error C3387 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3387"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3387"
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compiler Error C3387
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

member: атрибут \_\_declspec\(dllexport\) или \_\_declspec\(dllimport\) нельзя применять к члену управляемого типа или типа WinRT  
  
 Модификаторы `dllimport` и [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` недопустимы для членов управляемого типа или типа среды выполнения Windows.  
  
 В следующем примере показано возникновение ошибки C3387 и приводятся сведения по ее устранению.  
  
```  
// C3387a.cpp  
// compile with: /clr /c  
ref class X2 {  
   void __declspec(dllexport) mf() {   // C3387  
   // try the following line instead  
   // void mf() {  
   }  
};  
```