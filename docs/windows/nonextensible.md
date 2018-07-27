---
title: nonextensible | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87cdbf66676ed2a3e6054006270b39ad80325857
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881605"
---
# <a name="nonextensible"></a>nonextensible
Указывает, что `IDispatch` реализация содержит только свойства и методы, перечисленных в описании интерфейса и не могут быть расширены с помощью дополнительных членов во время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[nonextensible]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Nonextensible** языка C++ имеет ту же функциональность, что [nonextensible](http://msdn.microsoft.com/library/windows/desktop/aa367120) языка MIDL.  
  
 Использование **nonextensible** также требует [oleautomation](../windows/oleautomation.md) атрибута.  
  
## <a name="example"></a>Пример  
 Следующий код показывает один из способов использования **nonextensible** атрибута:  
  
```  
// cpp_attr_ref_nonextensible.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export] typedef long HRESULT;  
  
[dual, nonextensible, ms_union, oleautomation,   
uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   HRESULT procedure (int i);   
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`interface`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**Двойная** и **oleautomation**, или **disp-интерфейс**|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
