---
title: "Литералы XML и свойства оси XML не доступны во время этого сеанса отладки, так как они не используются в этой сборке | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31196"
  - "bc31196"
helpviewer_keywords: 
  - "BC31196"
ms.assetid: 36be5c92-dd6b-41d4-894a-2bd71d772092
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Литералы XML и свойства оси XML не доступны во время этого сеанса отладки, так как они не используются в этой сборке
На литерал XML или свойство оси XML была сделана ссылка в окне **Контрольные значения** или в окне **Интерпретация** во время сеанса отладки, в котором XML в [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] недоступен. Такое происходит в случае со сборкой, не использующей XML в [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] либо являющейся сборкой выпуска.  
  
 **Идентификатор ошибки:** BC31196  
  
### Исправление ошибки  
  
-   Начните новый сеанс отладки с использованием отладочной сборки.  
  
## См. также  
 [Отладка приложения в Visual Basic](../Topic/Debugging%20Your%20Visual%20Basic%20Application.md)   
 [XML\-литералы](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [Свойства оси XML](../Topic/XML%20Axis%20Properties%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)