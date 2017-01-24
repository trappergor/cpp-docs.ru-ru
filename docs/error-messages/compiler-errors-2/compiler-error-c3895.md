---
title: "Ошибка компилятора C3895 | Microsoft Docs"
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
  - "C3895"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3895"
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3895
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная": элементы данных "тип" не могут иметь тип volatile  
  
 Некоторые члены данных, например [literal](../../windows/literal-cpp-component-extensions.md) или [initonly](../../dotnet/initonly-cpp-cli.md), не могут иметь тип [volatile](../../cpp/volatile-cpp.md).  
  
 Следующий пример приводит к возникновению ошибки C3895:  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```