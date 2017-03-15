---
title: "Ошибка компилятора C2959 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2959"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2959"
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C2959
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

универсальный класс или функция не могут быть членом шаблона  
  
 Дополнительные сведения см. в разделах [Среда выполнения Windows и управляемые шаблоны](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md) и [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2959.  
  
```  
// C2959.cpp  
// compile with: /clr /c  
template <class T> ref struct S {  
   generic <class U> ref struct GR1;   // C2959  
};  
```