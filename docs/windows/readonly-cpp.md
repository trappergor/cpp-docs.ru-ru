---
title: "readonly (C++) | Microsoft Docs"
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
  - "vc-attr.readonly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "readonly - атрибут"
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# readonly (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Запрещает назначение элементу данных.  
  
## Синтаксис  
  
```  
  
[readonly]  
  
```  
  
## Заметки  
 Атрибут **readonly** языка C\+\+ имеет ту же функциональность, что и атрибут [readonly](http://msdn.microsoft.com/library/windows/desktop/aa367152) языка MIDL.  
  
 Если вы хотите запретить изменение параметра метода, используйте атрибут [in](../Topic/in%20\(C++\).md).  
  
## Пример  
 В следующем коде показано использование атрибута **readonly**:  
  
```  
// cpp_attr_ref_readonly.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
  
[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]  
__interface IFireTabCtrl  
{  
   [readonly, id(1)] int i();  
};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Data Member Attributes](../windows/data-member-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)