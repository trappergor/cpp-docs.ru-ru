---
title: "propputref | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.propputref"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propputref attribute"
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# propputref
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет функцию параметра свойства, которая использует ссылку вместо значения.  
  
## Синтаксис  
  
```  
  
[propputref]  
  
```  
  
## Заметки  
 **propputref** Атрибут C\+\+ имеет ту же функциональность, что и  [propputref](http://msdn.microsoft.com/library/windows/desktop/aa367147) атрибут MIDL.  
  
## Пример  
 См. пример [bindable](../windows/bindable.md) для использования образцы  **propputref**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|**propget**"  **propput**|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propput](../windows/propput.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)