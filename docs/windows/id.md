---
title: "id | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "id attribute"
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# id
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет a `dispid` параметр для функции\-члена \(или свойство или метод в интерфейсе или диспетчерский интерфейс\).  
  
## Синтаксис  
  
```  
  
      [ id(  
   dispid  
) ]  
```  
  
#### Параметры  
 `dispid`  
 Идентификатор менеджера для метода интерфейса.  
  
## Заметки  
 **id** Атрибут C\+\+ имеет ту же функциональность, что и  [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) атрибут MIDL.  
  
## Пример  
 См. пример [bindable](../windows/bindable.md) пример использования  **id**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод интерфейса|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Data Member Attributes](../windows/data-member-attributes.md)   
 [defaultvalue](../Topic/defaultvalue.md)   
 [in](../Topic/in%20\(C++\).md)   
 [выходной](../Topic/out%20\(C++\).md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)