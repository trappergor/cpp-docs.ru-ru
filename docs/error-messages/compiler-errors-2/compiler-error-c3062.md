---
title: "Ошибка компилятора C3062 | Microsoft Docs"
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
  - "C3062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3062"
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"перечисление": для перечислителя требуется значение, так как базовым типом является "тип"  
  
 Можно указать базовый тип перечисления.  При использовании некоторых типов необходимо присвоить значения каждому перечислению.  
  
 Дополнительные сведения о перечислениях см. в описании [класса enum](../../windows/enum-class-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3062:  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```