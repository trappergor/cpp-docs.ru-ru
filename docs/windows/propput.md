---
title: "propput | Microsoft Docs"
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
  - "vc-attr.propput"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propput attribute"
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# propput
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Задает функцию настройки свойства.  
  
## Синтаксис  
  
```  
  
[propput]  
  
```  
  
## Заметки  
 Атрибут **propput** языка C\+\+ имеет ту же функциональность, как и атрибут [propput](http://msdn.microsoft.com/library/windows/desktop/aa367146) языка MIDL.  
  
## Пример  
 См. пример для [bindable](../windows/bindable.md), где приведен пример использования **propput**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|**propget**, **propputref**|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propputref](../windows/propputref.md)