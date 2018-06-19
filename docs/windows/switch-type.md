---
title: switch_type | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.switch_type
dev_langs:
- C++
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1870e1ee623d8495e9f19dd8f32ea9382070bc14
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890187"
---
# <a name="switchtype"></a>switch_type
Определяет тип переменной, которая используется как дискриминантный объединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[switch_type(  
type  
}]  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `type`  
 Тип коммутатора, может быть целое число, символ, логическое значение, тип или тип перечисления.  
  
## <a name="remarks"></a>Примечания  
 **Switch_type** языка C++ имеет ту же функциональность, что [switch_type](http://msdn.microsoft.com/library/windows/desktop/aa367276) языка MIDL.  
  
 Атрибуты C++ не поддерживают [инкапсулированный объединения](http://msdn.microsoft.com/library/windows/desktop/aa366811). [Nonencapsulated объединения](http://msdn.microsoft.com/library/windows/desktop/aa367119) поддерживается только в следующей форме:  
  
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
  
## <a name="example"></a>Пример  
 В разделе [случай](../windows/case-cpp.md) пример приведен пример использования **switch_type**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`typedef`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
