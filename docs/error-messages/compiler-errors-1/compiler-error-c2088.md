---
title: "Ошибка компилятора C2088 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2088"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2088"
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2088
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

оператор: недопустим для "ключ класса"  
  
 Оператор не был определен для структуры или объединения.  Эта ошибка применима только к коду языка С.  
  
 Следующий пример проводит к генерированию трех ошибок C2088:  
  
```  
// C2088.c  
struct S {  
   int m_i;   
} s;  
  
int main() {  
   int i = s * 1;   // C2088  
   struct S s2 = +s;   // C2088  
   s++;   // C2088  
}  
```