---
title: "Ошибка компилятора C3418 | Microsoft Docs"
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
  - "C3418"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3418"
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3418
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

спецификатор доступа "спецификатор" не поддерживается  
  
 Спецификатор доступа среды CLR указан неправильно.  Для получения дополнительной информации см. [Видимость типов и членов](../Topic/Type%20and%20Member%20Visibility.md).  
  
## Пример  
 В следующем примере возникает ошибка C3418:  
  
```  
// C3418.cpp // compile with: /clr /c ref struct m { internal public:   // C3418 void test(){} }; ref struct n { internal:   // OK void test(){} };  
```