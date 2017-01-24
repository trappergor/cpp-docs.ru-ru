---
title: "Ошибка компилятора C2800 | Microsoft Docs"
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
  - "C2800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2800"
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

оператор "оператор" не может быть перегружен  
  
 Следующие операторы не могут быть перегружены: доступ к члену класса \(`.`\), указатель члена \(`.*`\), разрешение области действия \(`::`\), условное выражение \(`? :`\) и `sizeof`.  
  
 Следующий пример приводит к возникновению ошибки C2800:  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```