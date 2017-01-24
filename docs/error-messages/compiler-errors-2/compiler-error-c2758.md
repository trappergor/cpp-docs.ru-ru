---
title: "Ошибка компилятора C2758 | Microsoft Docs"
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
  - "C2758"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2758"
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2758
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

member: требуется инициализация члена ссылочного типа  
  
 Ошибка компилятора C2758 возникает, если конструктор не инициализирует член ссылочного типа в списке инициализаторов.  Компилятор оставляет член неопределенным.  Переменные ссылочного члена должны инициализироваться при объявлении или получать значение в списке инициализации конструктора.  
  
 Следующий пример приводит к возникновению ошибки C2758:  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```