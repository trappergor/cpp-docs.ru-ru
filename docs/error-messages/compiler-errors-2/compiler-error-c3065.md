---
title: "Ошибка компилятора C3065 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3065"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3065"
ms.assetid: e7a0bc69-1c68-459e-a7c4-93c65609ff7c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3065
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не допускается объявление свойства не в области класса  
  
 Модификатор [свойства](../../cpp/property-cpp.md) \_\_declspec использовался вне класса.  Свойства могут объявляться только внутри класса.  
  
 Следующий пример приводит к возникновению ошибки C3065:  
  
```  
// C3065.cpp // compile with: /c __declspec(property(get=get_i)) int i;   // C3065 class x { public: __declspec(property(get=get_i)) int i;   // OK };  
```