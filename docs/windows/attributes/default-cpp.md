---
title: по умолчанию (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 5fb7f205ccdf78e1ef64e2ba2c132e3c2b6b6000
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792480"
---
# <a name="default-c"></a>default (C++)

Указывает, что настраиваемый или disp-интерфейс, определенный в коклассе, представляет интерфейс программирования по умолчанию.

## <a name="syntax"></a>Синтаксис

```cpp
[ default(interface1, interface2) ]
```

### <a name="parameters"></a>Параметры

*interface1*<br/>
Интерфейс по умолчанию, который будет доступен в средах разработки сценариев, где создаются объекты на основе класса, определенного с помощью атрибута **default** .

Если исходный интерфейс по умолчанию не указан, в качестве интерфейса по умолчанию используется первое вхождение неисходного интерфейса.

*Interface2*<br/>
(Необязательно) Исходный интерфейс по умолчанию. Необходимо также указать этот интерфейс с [источника](source-cpp.md) атрибута.

Если исходный интерфейс по умолчанию не указан, в качестве интерфейса по умолчанию используется первый исходный интерфейс.

## <a name="remarks"></a>Примечания

**По умолчанию** атрибут C++ имеет ту же функциональность, что [по умолчанию](/windows/desktop/Midl/default) описании атрибута MIDL. **По умолчанию** атрибут также используется с [случай](case-cpp.md) атрибута.

## <a name="example"></a>Пример

В следующем коде показано, как **по умолчанию** используется в определении кокласса для указания `ICustomDispatch` качестве интерфейса программирования по умолчанию:

```cpp
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

[   coclass, default(ICustomDispatch), source(IDual), uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
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

[Источника](source-cpp.md) атрибут также содержит пример использования **по умолчанию**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**, элемент данных|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**Компонентный класс** (при применении к **класс** или **структуры**)|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[coclass](coclass.md)  