---
title: по умолчанию (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.default
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
ms.openlocfilehash: 291e16ad0967acd1869874fcc9fa6eb5529e4b44
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501686"
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

*интерфейс2*<br/>
Используемых Исходный интерфейс по умолчанию. Этот интерфейс также необходимо указать с помощью атрибута [source](source-cpp.md) .

Если исходный интерфейс по умолчанию не указан, в качестве интерфейса по умолчанию используется первый исходный интерфейс.

## <a name="remarks"></a>Примечания

Атрибут **default** языка C++ имеет ту же функциональность, что и атрибут [default](/windows/win32/Midl/default) языка MIDL. Атрибут **default** также используется вместе с атрибутом [case](case-cpp.md) .

## <a name="example"></a>Пример

В следующем коде показано, как **по умолчанию** используется определение кокласса для указания `ICustomDispatch` в качестве интерфейса программирования по умолчанию:

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

Атрибут [source](source-cpp.md) также содержит пример использования атрибута **default**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**класс**, **Структура**, элемент данных|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**coclass** (при применении к **классу** или **структуре**)|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[кокласс](coclass.md)