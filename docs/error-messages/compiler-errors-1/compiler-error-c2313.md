---
title: "Ошибка компилятора C2313 | Microsoft Docs"
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
  - "C2313"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2313"
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2313
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип1": перехват по ссылке \("тип2"\) в строке "номер"  
  
 Тип исключения имеет два обработчика. Тип второго перехвата — это ссылка на тип первого перехвата.  
  
 В следующем примере возникает ошибка C2313:  
  
```  
// C2313.cpp // compile with: /EHsc #include <eh.h> class C {}; int main() { try { throw "ooops!"; } catch( C& ) {} catch( C ) {}   // C2313 }  
```