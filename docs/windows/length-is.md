---
title: "length_is | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.length_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "length_is attribute"
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# length_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет количество элементов массива, которые необходимо передать.  
  
## Синтаксис  
  
```  
  
      [ length_is(  
   "expression"  
) ]  
```  
  
#### Параметры  
 *expression*  
 Одно или несколько выражений языка C.  Пустые ячейки аргумента допускаются.  
  
## Заметки  
 **length\_is** Атрибут C\+\+ имеет ту же функциональность, что и  [length\_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) атрибут MIDL.  
  
## Пример  
 См. [first\_is](../windows/first-is.md) пример, как определить раздел массива.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Поле `struct` OR  **union**параметр интерфейса, метод интерфейса|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [max\_is](../windows/max-is.md)   
 [last\_is](../windows/last-is.md)   
 [size\_is](../Topic/size_is.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)