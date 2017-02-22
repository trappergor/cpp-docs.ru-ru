---
title: "Ошибка компилятора C3113 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3113"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3113"
ms.assetid: 3afdc668-b29e-474e-9ea3-aa027d42db7c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C3113
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"структура" не может быть шаблоном или универсальным шаблоном  
  
 Была предпринята попытка создания шаблона класса или универсального шаблона класса на базе интерфейса или перечисления.  
  
 Следующий пример приводит к возникновению ошибки C3113:  
  
```  
// C3113.cpp  
// compile with: /c  
template <class T>   
enum E {};   // C3113  
// try the following line instead  
// class MyClass{};  
```