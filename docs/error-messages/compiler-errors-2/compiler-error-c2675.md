---
title: "Ошибка компилятора C2675 | Microsoft Docs"
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
  - "C2675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2675"
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

унарный "оператор": "тип" не определяет этот оператор, или преобразование в тип приемлемо для встроенного оператора  
  
 Ошибка C2675 также может возникать при использовании унарного оператора, когда тип не определяет оператор или преобразование в тип является приемлемым для предварительно определенного оператора.  Чтобы использовать оператор, необходимо перегрузить его для указанного типа или определить преобразование в тип, для которого определен оператор.  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C2675.  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```