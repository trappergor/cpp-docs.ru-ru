---
title: DefaultValue (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvalue
helpviewer_keywords:
- defaultvalue attribute
ms.assetid: efa5d050-b2cc-4d9e-9b8e-79954f218d3a
ms.openlocfilehash: 22aa969185afbac5ab395d0ac7dde23e715b8e58
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537674"
---
# <a name="defaultvalue"></a>defaultvalue

Позволяет задавать значение по умолчанию для типизированного необязательного параметра.

## <a name="syntax"></a>Синтаксис

```cpp
[ defaultvalue= value ]
```

### <a name="parameters"></a>Параметры

*значение*<br/>
Значение по умолчанию для параметра.

## <a name="remarks"></a>Примечания

**Defaultvalue** атрибут C++ имеет ту же функциональность, что [defaultvalue](/windows/desktop/Midl/defaultvalue) описании атрибута MIDL.

## <a name="example"></a>Пример

В следующем коде показан метод интерфейса с помощью **defaultvalue** атрибут:

```cpp
// cpp_attr_ref_defaultvalue.cpp
// compile with: /LD
#include <windows.h>

[export] typedef long HRESULT;
[export, ptr, string] typedef unsigned char * MY_STRING_TYPE;

[  uuid("479B29EE-9A2C-11D0-B696-00A0C903487A"), dual, oleautomation, helpstring("IFireTabCtrl Interface"), helpcontext(122), pointer_default(unique) ]

__interface IFireTabCtrl : IDispatch {
   [bindable, propget] HRESULT get_Size([out, retval, defaultvalue("33")] long *nSize);
   [bindable, propput] HRESULT put_Size([in] int nSize);
};

[ module(name="ATLFIRELib", uuid="479B29E1-9A2C-11D0-B696-00A0C903487A",    version="1.0", helpstring="ATLFire 1.0 Type Library") ];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[out](out-cpp.md)<br/>
[retval](retval.md)<br/>
[in](in-cpp.md)<br/>
[pointer_default](pointer-default.md)<br/>
[unique](unique-cpp.md)