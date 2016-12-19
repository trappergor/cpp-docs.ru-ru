---
title: "requires_category | Microsoft Docs"
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
  - "vc-attr.requires_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "requires_category attribute"
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# requires_category
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет категории необходимого компонента класса целевого объекта.  
  
## Синтаксис  
  
```  
  
     [ requires_category(   
  requires_category  
) ]  
```  
  
#### Параметры  
 *requires\_category*  
 Идентификатор необходимой категории.  
  
## Заметки  
 **requires\_category** Атрибут C\+\+ определяет категории компонентов необходим классом целевого объекта.  Дополнительные сведения см. в разделе REQUIRED\_CATEGORY.  
  
 Этот атрибут необходим [CoClass](../windows/coclass.md)"  [идентификатор progid](../Topic/progid.md)или  [vi\_progid](../windows/vi-progid.md) атрибут \(или другой атрибут, подразумевается одно из них\) также были применены к одному элементу.  
  
## Пример  
 В следующем примере кода требуется, чтобы реализовать объекта категория элемента управления.  
  
```  
// cpp_attr_ref_requires_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLibrary")];  
  
[ coclass, requires_category("CATID_Control"),  
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]  
class CMyClass {};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|Одно или несколько из следующих значений: **CoClass**"  **идентификатор progid**или  **vi\_progid**.|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [implements\_category](../Topic/implements_category.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)