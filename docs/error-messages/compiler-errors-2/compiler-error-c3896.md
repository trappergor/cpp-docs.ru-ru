---
title: "Ошибка компилятора C3896 | Microsoft Docs"
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
  - "C3896"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3896"
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3896
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : недопустимый инициализатор: этот литеральный элемент данных можно инициализировать только как 'nullptr'  
  
 Элемент данных [literal](../../windows/literal-cpp-component-extensions.md) неверное инициализирован.  Дополнительные сведения см. в разделе [nullptr](../../windows/nullptr-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3896:  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```