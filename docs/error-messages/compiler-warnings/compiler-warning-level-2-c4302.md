---
title: "Предупреждение компилятора (уровень 2) C4302 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4302"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4302"
ms.assetid: f5e1c939-e134-4cca-ba1e-9b15a81549ae
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 2) C4302
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

преобразование: усечение из "типа 1" к "типу 2"  
  
 Компилятор обнаружил преобразование большего типа в меньший.  Информация может быть потеряна.  
  
 Данное предупреждение по умолчанию отключено.  Дополнительные сведения см. в разделе [Отключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
 Следующий пример приводит к возникновению ошибки C4302:  
  
```  
// C4302.cpp  
// compile with: /W2  
#pragma warning(default : 4302)  
int main() {  
   int i;  
   char c = (char) &i;     // C4302  
   short s = (short) &i;   // C4302  
}  
```