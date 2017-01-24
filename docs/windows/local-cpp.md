---
title: "local (C++) | Microsoft Docs"
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
  - "vc-attr.local"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "local attribute"
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# local (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При использовании в заголовке интерфейса позволяет использовать компилятора MIDL как генератор заголовка.  При использовании в отдельной функции обозначает локальную процедуру, для которой нет заглушки не формируются.  
  
## Синтаксис  
  
```  
  
[local]  
  
```  
  
## Заметки  
 `local` Атрибут C\+\+ имеет ту же функциональность, что и  [Локальная](http://msdn.microsoft.com/library/windows/desktop/aa367071) атрибут MIDL.  
  
## Пример  
 См. [call\_as](../windows/call-as.md) пример использования  `local`.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`метод интерфейса|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|**dispinterface**|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [call\_as](../windows/call-as.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)