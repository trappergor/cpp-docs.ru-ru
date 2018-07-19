---
title: по умолчанию (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.default
dev_langs:
- C++
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb701b91fc1e076dcf4e6540bf8bcaf6141ec6c6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872969"
---
# <a name="default-c"></a>default (C++)
Указывает, что настраиваемый или disp-интерфейс, определенный в коклассе, представляет интерфейс программирования по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ default(  
   interface1,  
   interface2  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *interface1*  
 Интерфейс по умолчанию, который будет доступен в средах разработки сценариев, где создаются объекты на основе класса, определенного с помощью атрибута **default** .  
  
 Если исходный интерфейс по умолчанию не указан, в качестве интерфейса по умолчанию используется первое вхождение неисходного интерфейса.  
  
 *interface2*(необязательно)  
 Исходный интерфейс по умолчанию. Этот интерфейс также необходимо указать с помощью атрибута [source](../windows/source-cpp.md) .  
  
 Если исходный интерфейс по умолчанию не указан, в качестве интерфейса по умолчанию используется первый исходный интерфейс.  
  
## <a name="remarks"></a>Примечания  
 Атрибут **default** языка C++ имеет ту же функциональность, что и атрибут [default](http://msdn.microsoft.com/library/windows/desktop/aa366787) языка MIDL. Атрибут **default** также используется вместе с атрибутом [case](../windows/case-cpp.md) .  
  
## <a name="example"></a>Пример  
 В приведенном далее коде показано использование атрибута **default** в определении кокласса для указания **ICustomDispatch** в качестве интерфейса программирования по умолчанию.  
  
```  
// cpp_attr_ref_default.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]   
__interface IDual {  
   HRESULT Dual([in] long l, [out, retval] long *pLong);  
};  
  
[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustomDispatch : public IDispatch {  
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);  
};  
  
[   coclass,  
   default(ICustomDispatch),   
   source(IDual),  
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]  
class CClass : public ICustom, public IDual, public ICustomDispatch {  
   HRESULT Custom(long l, long *pLong) { return(S_OK); }  
   HRESULT Dual(long l, long *pLong) { return(S_OK); }  
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }  
};  
  
int main() {  
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch  
   CClass *pClass = new CClass;  
  
   long llong;  
  
   pClass->custom(1, &llong);  
   pClass->dual(1, &llong);  
   pClass->dispinterface(1, &llong);  
   pClass->dispatch(1, &llong);  
  
   delete pClass;  
#endif  
   return(0);  
}  
```  
  
 Атрибут [source](../windows/source-cpp.md) также содержит пример использования атрибута **default**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**, `struct`, элемент данных|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**кокласс** (при применении к **классу** или `struct`)|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [coclass](../windows/coclass.md)   
