---
title: nonextensible | Документация Майкрософт
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
ms.openlocfilehash: 2f670da3ad4858f3c09903f2ed3ec6aa58268180
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608499"
---
# <a name="nonextensible"></a>nonextensible
Указывает, что `IDispatch` реализация содержит только свойства и методы, перечисленных в описании интерфейса и не может быть расширен с помощью дополнительных членов во время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[nonextensible]  
```  
  
## <a name="remarks"></a>Примечания  
 **Nonextensible** атрибут C++ имеет ту же функциональность, что [nonextensible](http://msdn.microsoft.com/library/windows/desktop/aa367120) описании атрибута MIDL.  
  
 Использование **nonextensible** также требуется [oleautomation](../windows/oleautomation.md) атрибута.  
  
## <a name="example"></a>Пример  
 В следующем коде показано один из способов использования **nonextensible** атрибут:  
  
```cpp  
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
|**Применение**|**interface**|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|`dual` и `oleautomation`, или `dispinterface`|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   