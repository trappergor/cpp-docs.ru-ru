---
title: "Ошибка компилятора C3460 | Microsoft Docs"
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
  - "C3460"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3460"
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3460
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": только пользовательские типы могут перенаправляться  
  
 Для получения дополнительной информации см. [Перенаправление типов \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Пример  
 В следующем примере создается компонент.  
  
```  
// C3460.cpp // compile with: /LD /clr public ref class R {};  
```  
  
## Пример  
 В следующем примере возникает ошибка C3460.  
  
```  
// C3460_b.cpp // compile with: /clr /c #using "C3460.dll" [assembly:TypeForwardedTo(int::typeid)];   // C3460 [assembly:TypeForwardedTo(R::typeid)];  
```