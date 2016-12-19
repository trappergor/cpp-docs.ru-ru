---
title: "Ошибка компилятора C2739 | Microsoft Docs"
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
  - "C2739"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2739"
ms.assetid: 5b63e435-7631-43d7-805e-f2adefb7e517
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2739
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

number: явно задаваемый управляемый массив или массив WinRT может иметь размерность от 1 до 32  
  
 Измерение массива не входило в диапазон от 1 до 32.  
  
 В следующем примере показано возникновение ошибки C2739 и приводятся сведения по ее устранению.  
  
```  
// C2739.cpp  
// compile with: /clr  
int main() {  
   array<int, -1>^a;   // C2739  
   // try the following line instead  
   // array<int, 2>^a;  
}  
```