---
title: "pointer_default | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.pointer_default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_default attribute"
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# pointer_default
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет атрибут по умолчанию указателя для всех указателей, кроме верхнего уровня указатели, отображаемые в списки параметров.  
  
## Синтаксис  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### Параметры  
 *значение*  
 Значение, которое описывает тип указателя. **ptr**"  `ref`или  **unique**.  
  
## Заметки  
 **pointer\_default** Атрибут C\+\+ имеет ту же функциональность, что и  [pointer\_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) атрибут MIDL.  
  
## Пример  
 Эти пример [defaultvalue](../Topic/defaultvalue.md) для использования образцы  **pointer\_default**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)