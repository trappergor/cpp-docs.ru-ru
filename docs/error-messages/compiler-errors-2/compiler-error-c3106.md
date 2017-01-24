---
title: "Ошибка компилятора C3106 | Microsoft Docs"
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
  - "C3106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3106"
ms.assetid: 39d97a32-0905-4702-87d3-7f8ce473fb93
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3106
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"атрибут": неименованные аргументы должны следовать перед именованными  
  
 Неименованные аргументы должны передаваться атрибуту перед именованными аргументами.  
  
 Для получения дополнительной информации см. [Пользовательские атрибуты](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3106.  
  
```  
// C3106.cpp  
// compile with: /c  
[module(name="MyLib", dll)];   // C3106  
[module(dll, name="MyLib")];   // OK  
```