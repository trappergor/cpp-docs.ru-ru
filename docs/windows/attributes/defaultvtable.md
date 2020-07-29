---
title: defaultvtable (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvtable
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
ms.openlocfilehash: 2da0d8070f961f1ae0fc075585eb28881f712fb4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215261"
---
# <a name="defaultvtable"></a>defaultvtable

Определяет интерфейс как интерфейс vtable по умолчанию для COM-объекта.

## <a name="syntax"></a>Синтаксис

```cpp
[ defaultvtable(interface) ]
```

### <a name="parameters"></a>Параметры

*interface*<br/>
Указанный интерфейс, для которого требуется использовать vtable по умолчанию для COM-объекта.

## <a name="remarks"></a>Remarks

Атрибут **defaultvtable** C++ имеет те же функциональные возможности, что и атрибут [defaultvtable](/windows/win32/Midl/defaultvtable) MIDL.

## <a name="example"></a>Пример

В следующем коде показаны атрибуты класса, которые используют **defaultvtable** для указания интерфейса по умолчанию:

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
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)
