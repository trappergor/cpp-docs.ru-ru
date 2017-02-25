---
title: "Ошибка компилятора C2798 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2798"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2798"
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2798
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

неоднозначный "super::member"  
  
 Несколько унаследованных структур содержат член, на который существует ссылка [super](../../cpp/super.md).  Можно устранить ошибку одним из следующих способов:  
  
-   Удаление B1 или B2 из списка наследования D.  
  
-   Изменение имени члена данных в B1 или B2.  
  
 Следующий пример приводит к возникновению ошибки C2798:  
  
```  
// C2798.cpp  
struct B1 {  
   int i;  
};  
  
struct B2 {  
   int i;  
};  
  
struct D : B1, B2 {  
   void g() {  
      __super::i = 4; // C2798  
   }  
};  
```