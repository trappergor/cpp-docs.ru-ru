---
title: "Ошибка компилятора C3880 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3880"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3880"
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C3880
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

var: не могут быть данными\-членом литерала  
  
 Тип атрибута [литерал](../../windows/literal-cpp-component-extensions.md) должен существовать или быть преобразован во время компиляции в один из следующих типов:  
  
-   целые типы  
  
-   string  
  
-   перечисление с целым или базовым типом.  
  
 Следующий пример приводит к возникновению ошибки C3880:  
  
```  
// C3880.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal System::Decimal staticConst1 = 10;   // C3880  
   literal int staticConst2 = 10;   // OK  
};  
```