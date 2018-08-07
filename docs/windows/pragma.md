---
title: директивы pragma | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pragma
dev_langs:
- C++
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5abd483fb5a680ac3dba4ec01fc4bc6ebfa09ef2
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602621"
---
# <a name="pragma"></a>pragma
Создает указанную строку в созданного IDL-файла без использования кавычек. 
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ pragma(  
   pragma_statement  
) ];  
```  
  
#### <a name="parameters"></a>Параметры  
 *pragma_statement*  
 Директива pragma, который вы хотите перейти на созданного IDL-файла.  
  
## <a name="remarks"></a>Примечания  
 **Pragma** атрибут C++ имеет ту же функциональность, что [pragma](http://msdn.microsoft.com/library/windows/desktop/aa367143) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cpp_attr_ref_pragma.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[pragma(pack(4))];  
  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A  
{  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В любом месте|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
 [pack](../preprocessor/pack.md)   