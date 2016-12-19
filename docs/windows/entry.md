---
title: "entry | Microsoft Docs"
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
  - "vc-attr.entry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "entry attribute"
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# entry
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет, экспортированные функции или константы в модуле, указав точки входа в DLL.  
  
## Синтаксис  
  
```  
  
      [ entry(  
   id  
) ]  
```  
  
#### Параметры  
 `id`  
 Идентификатор точки входа.  
  
## Заметки  
 **запись** Атрибут C\+\+ имеет ту же функциональность, что и  [запись](http://msdn.microsoft.com/library/windows/desktop/aa366815) атрибут MIDL.  
  
## Пример  
 См. пример [idl\_module](../windows/idl-module.md) для использования примера  **запись**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Атрибут `idl_module`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)