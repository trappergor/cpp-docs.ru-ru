---
title: "Ошибка компилятора C2499 | Microsoft Docs"
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
  - "C2499"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2499"
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2499
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

класс: класс не может выступать в качестве базового для себя самого  
  
 Была предпринята попытка указать класс, который был определен как базовый класс.  
  
 Следующий пример приводит к возникновению ошибки C2499:  
  
```  
// C2499.cpp  
// compile with: /c  
class CMyClass : public CMyClass {};   // C2499  
class CMyClass{};   // OK  
```