---
title: iid_is | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.iid_is
dev_langs:
- C++
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 508f83b1dde590a4a8a04980895ef247f2a16123
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014992"
---
# <a name="iidis"></a>iid_is
Указывает идентификатор IID интерфейса COM, на которые указывает указатель интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
[ iid_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>Параметры  
 *Выражение*  
 Выражение языка C, которое указывает IID COM-интерфейса, на который указывает указатель интерфейса.  
  
## <a name="remarks"></a>Примечания  
 **Iid_is** атрибут C++ имеет ту же функциональность, что [iid_is](http://msdn.microsoft.com/library/windows/desktop/aa367044) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 В следующем коде показано использование **iid_is**:  
  
```cpp  
// cpp_attr_ref_iid_is.cpp  
// compile with: /LD  
#include "wtypes.h"  
#include "unknwn.h"  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl : IDispatch  
{  
   [id(1)] HRESULT CreateInstance([in] REFIID riid,[out, iid_is("riid")]   
   IUnknown ** ppvObject);  
};  
  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Параметр интерфейса, элемент данных|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   