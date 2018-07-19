---
title: uidefault | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.uidefault
dev_langs:
- C++
helpviewer_keywords:
- uidefault attribute
ms.assetid: 200de0e0-2e34-40a2-bae4-8d485a62264d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ad24d6e874b1c2efd9b57118e20fe78bfa037bd3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890155"
---
# <a name="uidefault"></a>uidefault
Указывает, что элемент информации о типе является элементом по умолчанию, для отображения в пользовательском интерфейсе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[uidefault]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Uidefault** языка C++ имеет ту же функциональность, что [uidefault](http://msdn.microsoft.com/library/windows/desktop/aa367292) языка MIDL.  
  
## <a name="example"></a>Пример  
 Следующий код показывает образец **uidefault**:  
  
```  
// cpp_attr_ref_uidefault.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom{  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
   [uidefault]HRESULT id0([in] long l);  
   [uidefault]HRESULT id1([in] long l);  
  
   [uidefault, propget] HRESULT get_y(int *y);  
   [uidefault, propput] HRESULT put_y(int y);  
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
 [Атрибуты метода](../windows/method-attributes.md)   
