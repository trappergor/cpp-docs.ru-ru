---
title: "Ошибка компилятора C3669 | Microsoft Docs"
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
  - "C3669"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3669"
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3669
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

член: спецификатор переопределения "override" недопустим в статических функциях\-членах или конструкторах  
  
 Перегрузка была указана некорректно.  Дополнительные сведения см. в разделе [Явное переопределение](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3669:  
  
```  
// C3669.cpp  
// compile with: /clr  
public ref struct R {  
   R() override {}   // C3669  
};  
```