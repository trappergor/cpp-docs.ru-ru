---
title: "switch_type | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.switch_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "switch_type attribute"
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# switch_type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает тип переменной, используемой в качестве соединение дискриминантное.  
  
## Синтаксис  
  
```  
  
[switch_type(  
type  
}]  
  
```  
  
#### Параметры  
 `type`  
 Тип переключателя, может быть целым числом, знаком, типом логического или перечисления.  
  
## Заметки  
 **switch\_type** Атрибут C\+\+ имеет ту же функциональность, что и  [switch\_type](http://msdn.microsoft.com/library/windows/desktop/aa367276) атрибут MIDL.  
  
 Атрибуты C\+\+ не поддерживают [инкапсулированные соединения](http://msdn.microsoft.com/library/windows/desktop/aa366811).  [соединения Nonencapsulated](http://msdn.microsoft.com/library/windows/desktop/aa367119) поддерживаются только в следующей форме:  
  
```  
// cpp_attr_ref_switch_type.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
[ export ]  
struct SizedValue2 {  
   [switch_type("char"), switch_is(kind)] union {  
      [case(1), string]  
         wchar_t* wval;  
      [default, string]  
         char* val;  
   };  
   char kind;  
};  
```  
  
## Пример  
 См. [case](../windows/case-cpp.md) пример использования образца  **switch\_type**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`typedef`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)