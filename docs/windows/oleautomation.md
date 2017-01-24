---
title: "oleautomation | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.oleautomation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "oleautomation attribute"
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# oleautomation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, что интерфейс совместимый с автоматизацией.  
  
## Синтаксис  
  
```  
  
[oleautomation]  
  
```  
  
## Заметки  
 **oleautomation** Атрибут C\+\+ имеет ту же функциональность, что и  [oleautomation](http://msdn.microsoft.com/library/windows/desktop/aa367129) атрибут MIDL.  
  
## Пример  
 См. примеры [defaultvalue](../Topic/defaultvalue.md) и  [nonextensible](../Topic/nonextensible.md) для использования образцы  **oleautomation**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|**dispinterface**|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)