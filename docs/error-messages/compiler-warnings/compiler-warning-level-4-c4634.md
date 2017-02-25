---
title: "Предупреждение компилятора (уровень&#160;4) C4634 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4634"
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Предупреждение компилятора (уровень&#160;4) C4634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Комментарий XML\-документа: применить невозможно: причина  
  
 Теги XML\-документации могут применяться не ко всем конструкциям C\+\+.  Например, нельзя добавить комментарий документации к пространству имен или шаблону.  
  
 Дополнительные сведения см. в разделе [Документация XML](../../ide/xml-documentation-visual-cpp.md).  
  
## Пример  
 Следующий пример приводит к возникновению предупреждения C4634.  
  
```  
// C4634.cpp // compile with: /W4 /doc /c /// This is a namespace.   // C4634 namespace hello { class MyClass  {}; };  
```  
  
## Пример  
 Следующий пример приводит к возникновению предупреждения C4634.  
  
```  
// C4634_b.cpp // compile with: /W4 /doc /c /// This is a template.   // C4634 template <class T> class MyClass  {};  
```