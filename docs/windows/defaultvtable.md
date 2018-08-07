---
title: defaultvtable | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultvtable
dev_langs:
- C++
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 83949616f204ae37b42b91b03d69d8d803a1582f
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569674"
---
# <a name="defaultvtable"></a>defaultvtable
Определяет интерфейс как интерфейс по умолчанию vtable для COM-объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ defaultvtable(  
   interface  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *interface*  
 Указанный интерфейс, который вы хотите иметь vtable по умолчанию для COM-объекта.  
  
## <a name="remarks"></a>Примечания  
 **Defaultvtable** атрибут C++ имеет ту же функциональность, что [defaultvtable](http://msdn.microsoft.com/library/windows/desktop/aa366795) описании атрибута MIDL.  
  
## <a name="example"></a>Пример  
 В следующем коде показано атрибуты для класса, используйте **defaultvtable** для указания интерфейс по умолчанию:  
  
```cpp  
// cpp_attr_ref_defaultvtable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI1 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMyI2 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000003")]  
__interface IMyI3 {  
   HRESULT x();  
};  
  
[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),  
uuid("00000000-0000-0000-0000-000000000004")]  
class CMyC3 : public IMyI3 {};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**Класс**, **структуры**|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**coclass**|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   