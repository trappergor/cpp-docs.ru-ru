---
title: "Ошибка компилятора C3320 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3320"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3320"
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3320
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": имя типа не может совпадать со свойством name модуля  
  
 Экспортированный определяемый пользователем тип \(UDT\), который может быть структурой, классом, перечислением, объединением или [\_\_value](../../misc/value.md), не может иметь то же имя, что и параметр, передаваемый в свойство имени атрибута [module](../../windows/module-cpp.md).  
  
 Следующий пример приводит к возникновению ошибки C3320:  
  
```  
// C3320.cpp #include "unknwn.h" [module(name="xx")]; [export] struct xx {   // C3320 // Try the following line instead // [export] struct yy { int i; };  
```