---
title: "Ошибка компилятора C3238 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3238"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3238"
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3238
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": тип с этим именем уже перенаправлен в сборку "сборка"  
  
 В клиентском приложении был определен тип, который также определен посредством синтаксиса перенаправления в связанной сборке. Нельзя определять оба типа в области приложения.  
  
 Дополнительные сведения см. в разделе [Перенаправление типов \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Пример  
 В следующем примере создается сборка, содержащая тип, перенаправленный из другой сборки.  
  
```  
// C3238.cpp // compile with: /clr /LD public ref class R {};  
```  
  
## Пример  
 В следующем примере создается сборка, которая используется для содержания определения типа, но содержит не только синтаксис перенаправления для типа.  
  
```  
// C3238_b.cpp // compile with: /clr /LD #using "C3238.dll" [ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3238.  
  
```  
// C3238_c.cpp // compile with: /clr /c // C3238 expected // Delete the following line to resolve. #using "C3238_b.dll" public ref class R {};  
```