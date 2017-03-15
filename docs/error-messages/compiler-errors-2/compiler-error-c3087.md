---
title: "Ошибка компилятора C3087 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3087"
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Ошибка компилятора C3087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"именованный\_аргумент": вызов атрибута "атрибут" уже инициализирует данный член  
  
 Именованный аргумент был указан в том же блоке атрибута, что и неименованный аргумент для того же значения. Укажите только именованный или неименованный аргумент.  
  
## Пример  
 В следующем примере возникает ошибка C3087:  
  
```  
// C3087.cpp // compile with: /c [idl_quote("quote1", text="quote2")];   // C3087 [idl_quote(text="quote3")];   // OK [idl_quote("quote4")];   // OK  
```