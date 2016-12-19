---
title: "Ошибка компилятора C2229 | Microsoft Docs"
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
  - "C2229"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2229"
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2229
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

тип "идентификатор" имеет недопустимый массив нулевого размера  
  
 Член структуры или битовое поле содержит массив нулевого размера, который не является последним членом.  
  
 Поскольку массив нулевого размера может использоваться в качестве последнего члена структуры, при выделении памяти для этой структуры необходимо указать его размер.  
  
 Если массив нулевого размера не является последним членом структуры, то компилятор не может вычислить смещение для оставшихся полей.  
  
 Следующий пример приводит к возникновению ошибки C2229:  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```