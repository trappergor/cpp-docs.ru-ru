---
title: "Атрибут System.Diagnostics.DebuggerHiddenAttribute не влияет на Get или Set при применении к определению свойств | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40051"
  - "vbc40051"
helpviewer_keywords: 
  - "BC40051"
ms.assetid: 623d5e48-7fb2-48a9-bbbb-92914b08c01c
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Атрибут System.Diagnostics.DebuggerHiddenAttribute не влияет на Get или Set при применении к определению свойств
Атрибут System.Diagnostics.DebuggerHiddenAttribute не влияет на Get или Set при применении к определению свойств. Примените атрибут непосредственно к процедурам Get и Set соответствующим образом.  
  
 Атрибут <xref:System.Diagnostics.DebuggerHiddenAttribute> применяется к объявлению свойств.  
  
 Исходный код может применять <xref:System.Diagnostics.DebuggerHiddenAttribute> к процедуре. Это указывает отладчику Visual Studio не останавливаться внутри процедуры и не разрешать устанавливать в процедуре какие\-либо точки останова.  
  
 Хотя вы можете применить <xref:System.Diagnostics.DebuggerHiddenAttribute> к свойству, это не оказывает никакого действия. Этот атрибут оказывает нужное вам действие, только если применить его к процедуре `Get` или `Set` свойства.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о скрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Идентификатор ошибки:** BC40051  
  
### Исправление ошибки  
  
-   Удалите <xref:System.Diagnostics.DebuggerHiddenAttribute> из объявления свойства и примените его к процедуре `Get` или `Set` свойства соответственно.  
  
## См. также  
 <xref:System.Diagnostics.DebuggerHiddenAttribute>   
 [Процедуры свойств](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [Оператор Property](../Topic/Property%20Statement.md)   
 [Оператор Get](../Topic/Get%20Statement.md)   
 [Оператор Set](../Topic/Set%20Statement%20\(Visual%20Basic\).md)