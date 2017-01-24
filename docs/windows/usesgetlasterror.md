---
title: "usesgetlasterror | Microsoft Docs"
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
  - "vc-attr.usesgetlasterror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "usesgetlasterror attribute"
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# usesgetlasterror
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает участника, что если ошибка вызывающий эту функцию, то вызывающий может вызвать `GetLastError` извлечь код ошибки.  
  
## Синтаксис  
  
```  
  
[usesgetlasterror]  
  
```  
  
## Заметки  
 **usesgetlasterror** Атрибут C\+\+ имеет ту же функциональность, что и  [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) атрибут MIDL.  
  
## Пример  
 См. [idl\_module](../windows/idl-module.md) пример образца, как использовать  **usesgetlasterror**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**Модуль** атрибут|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)