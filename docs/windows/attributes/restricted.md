---
title: Restricted (атрибут COM C++)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.restricted
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
ms.openlocfilehash: 0545c07936c59a59dd4712f4b0a2fd98a6701f2e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230030"
---
# <a name="restricted"></a>restricted

Указывает, что член модуля, интерфейс или disp-интерфейса не может вызываться произвольным образом.

## <a name="syntax"></a>Синтаксис

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>Параметры

*interfaces*;<br/>
Один или несколько интерфейсов, которые не могут вызываться произвольно для COM-объекта. Этот параметр допустим только при применении к классу.

## <a name="remarks"></a>Remarks

Атрибут **ограниченного** C++ имеет те же функциональные возможности, что и [ограниченный](/windows/win32/Midl/restricted) атрибут MIDL.

## <a name="example"></a>Пример

В следующем коде показано, как использовать атрибут **Restricted** :

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Метод интерфейса, **интерфейс**, **`class`** ,**`struct`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|**coclass** (при применении к **`class`** или **`struct`** )|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)
