---
title: "Ошибка компилятора C2720 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2720"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2720"
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2720
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

identifier: недопустимый спецификатор класса хранения specifier для членов  
  
 Класс хранения нельзя использовать для членов класса вне объявления.  Чтобы устранить эту ошибку, удалите ненужный [спецификатор класса хранения](http://msdn.microsoft.com/ru-ru/10b3d22d-cb40-450b-994b-08cf9a211b6c) из определения члена вне объявления класса.  
  
 В следующем примере показано возникновение ошибки C2720 и приводятся сведения по ее устранению.  
  
```  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
  
```