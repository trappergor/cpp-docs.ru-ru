---
title: "Ошибка компилятора C3347 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3347"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3347"
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3347
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"arg": обязательный аргумент не указан в атрибуте "idl\_module"  
  
 Обязательный аргумент не передан в атрибут [idl\_module](../../windows/idl-module.md).  
  
 Следующий пример приводит к возникновению ошибки C3347:  
  
```  
// C3347.cpp // compile with: /c [module(name="xx")]; [idl_module(dllname="x")];    // C3347 // try the following line instead // [idl_module(name="test", dllname="x")];  
```