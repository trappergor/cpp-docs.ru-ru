---
title: "Ошибка компилятора C3247 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3247"
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс1": класс coclass не может наследовать от другого класса coclass "класс2"  
  
 Класс, помеченный атрибутом [coclass](../../windows/coclass.md), не может наследовать от другого класса, помеченного атрибутом `coclass`.  
  
 Следующий пример приводит к возникновению ошибки C3247:  
  
```  
// C3247.cpp [module(name="MyLib")]; [coclass] class a { }; [coclass] class b : public a {   // C3247 }; int main() { }  
```