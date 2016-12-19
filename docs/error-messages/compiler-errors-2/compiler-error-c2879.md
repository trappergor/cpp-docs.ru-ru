---
title: "Ошибка компилятора C2879 | Microsoft Docs"
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
  - "C2879"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2879"
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2879
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ": при определении псевдонима пространства имен альтернативное имя может быть присвоено только существующему пространству имен  
  
 Невозможно создать [псевдоним пространства имен](../Topic/namespace%20Alias.md) для символа, отличного от пространства имен.  
  
 Следующий пример приводит к возникновению ошибки C2879:  
  
```  
// C2879.cpp  
int main() {  
   int i;  
   namespace A = i;   // C2879 i is not a namespace  
}  
```