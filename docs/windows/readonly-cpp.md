---
title: только для чтения (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.readonly
dev_langs:
- C++
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b4f4e6d7c3941b1e90e0c49d113afe02dfcd491
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604428"
---
# <a name="readonly-c"></a>readonly (C++)
Запрещает назначение элементу данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[readonly]  
```  
  
## <a name="remarks"></a>Примечания  
 Атрибут **readonly** языка C++ имеет ту же функциональность, что и атрибут [readonly](http://msdn.microsoft.com/library/windows/desktop/aa367152) языка MIDL.  
  
 Если вы хотите запретить изменение параметра метода, используйте атрибут [in](../windows/in-cpp.md) .  
  
## <a name="example"></a>Пример  
 В следующем коде показано использование атрибута **readonly** :  
  
```cpp  
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
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты элементов данных](../windows/data-member-attributes.md)   