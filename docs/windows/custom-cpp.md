---
title: "custom (C++) | Microsoft Docs"
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
  - "vc-attr.custom"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "custom attributes, defining"
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# custom (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет метаданные для объекта в библиотеке типов.  
  
## Синтаксис  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### Параметры  
 *uuid*  
 Уникальный идентификатор.  
  
 *значение*  
 Значение, которое можно поместить в тип variant.  
  
## Заметки  
 **custom** Атрибут C\+\+ в результате чего данные располагаться в библиотеку типов.  Необходимо средство, которое считывает пользовательское значение из библиотеки типов.  
  
 **custom** атрибут имеет ту же функциональность, что и  [custom](http://msdn.microsoft.com/library/windows/desktop/aa366766) атрибут MIDL.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Non\-модель COM `interface`"  **класс**"  `enum`\- s  `idl_module` методы члены интерфейса, параметры интерфейса  `typedef`\- s  **union**\- s  `struct`s|  
|**Repeatable**|Да|  
|**Обязательные атрибуты**|CoClass \(при использовании в классе\)|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)