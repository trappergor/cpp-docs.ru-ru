---
title: "Тип ограничения общего параметра &lt;typename&gt; несовместим с CLS | Microsoft Docs"
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
  - "bc40040"
  - "vbc40040"
helpviewer_keywords: 
  - "BC40040"
ms.assetid: c640dd59-56a9-43ed-b199-32a60f7b9b06
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Тип ограничения общего параметра &lt;typename&gt; несовместим с CLS
Универсальный тип помечен как `<CLSCompliant(True)>`, но ограничение одного из параметров типов указывает на тип, который помечен как `<CLSCompliant(False)>`, не помечен или имеет несоответствующий тип.  
  
 Чтобы тип соответствовал [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), он должен использовать только типы, соответствующие CLS. Это применяется также к ограничениям в параметрах универсального типа.  
  
 Следующие типы данных [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] не соответствуют CLS:  
  
-   [Тип данных SByte](../Topic/SByte%20Data%20Type%20\(Visual%20Basic\).md)  
  
-   [Тип данных UInteger](../Topic/UInteger%20Data%20Type.md)  
  
-   [Тип данных ULong](../Topic/ULong%20Data%20Type%20\(Visual%20Basic\).md)  
  
-   [Тип данных UShort](../Topic/UShort%20Data%20Type%20\(Visual%20Basic\).md)  
  
 Когда вы применяете атрибут <xref:System.CLSCompliantAttribute> к программному элементу, вы задаете для параметра `isCompliant` атрибута значение `True` или `False`, чтобы указать на соответствие или несоответствие требованиям. Для этого параметра нет значения по умолчанию, и вы должны предоставить его.  
  
 Если вы не примените <xref:System.CLSCompliantAttribute> к элементу, он считается не соответствующим требованиям.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Идентификатор ошибки:** BC40040  
  
### Исправление ошибки  
  
-   Если универсальный тип должен принять параметр типа, ограниченный этим типом, удалите <xref:System.CLSCompliantAttribute>. Тип не может соответствовать CLS.  
  
-   Если универсальный тип должен соответствовать CLS, измените тип этого ограничения на ближайший тип, соответствующий CLS. Например, вместо `UInteger` вы можете использовать `Integer`, если вам не нужен диапазон значений, превышающий 2 147 483 647. Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.  
  
## См. также  
 [Универсальные типы в Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [\<PAVE OVER\> Запись кода, соответствующего CLS](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)