---
title: "Ошибка компилятора C3466 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3466"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3466"
ms.assetid: 69a877d9-a749-474b-bfc3-8d3fd53ba8fd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C3466
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": невозможно переадресовать специализацию универсального класса  
  
 Невозможно использовать переадресацию типа для специализации универсального класса.  
  
 Для получения дополнительной информации см. [Перенаправление типов \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Пример  
 В следующем примере показано создание компонента.  
  
```  
// C3466.cpp  
// compile with: /clr /LD  
generic<typename T>  
public ref class GR {};  
  
public ref class GR2 {};  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3466.  
  
```  
// C3466_b.cpp  
// compile with: /clr /c  
#using "C3466.dll"  
[assembly:TypeForwardedTo(GR<int>::typeid)];   // C3466  
[assembly:TypeForwardedTo(GR2::typeid)];   // OK  
```