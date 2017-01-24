---
title: "Ошибка компилятора C3075 | Microsoft Docs"
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
  - "C3075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3075"
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"экземпляр": нельзя внедрить экземпляр ссылочного типа "тип" в тип значения  
  
 Тип значения не может содержать экземпляр ссылочного типа.  
  
 Для получения дополнительной информации см. [Семантика стека C\+\+ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3075:  
  
```  
// C3075.cpp // compile with: /clr /c ref struct U {}; value struct X { U y;   // C3075 }; ref struct Y { U y;   // OK };  
```