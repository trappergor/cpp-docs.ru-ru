---
title: "restricted | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.restricted"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "restricted attribute"
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# restricted
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, что член модуля, интерфейса или диспетчерский интерфейс не может вызываться произвольным образом.  
  
## Синтаксис  
  
```  
  
      [ restricted(  
   interfaces  
) ]  
```  
  
#### Параметры  
 `interfaces`  
 Один или несколько интерфейсов, которые не могут быть вызваны произвольно com\-объекта.  Этот параметр допустим только при применении к классу.  
  
## Заметки  
 **restricted** Атрибут C\+\+ имеет ту же функциональность, что и  [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) атрибут MIDL.  
  
## Пример  
 В следующем примере кода демонстрируется применение restricted атрибут:  
  
```  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод интерфейса `interface`"  **класс**"  `struct`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|**CoClass** \(при применении к  **класс** OR  `struct`\)|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)