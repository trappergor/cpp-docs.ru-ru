---
title: Restricted (C++ атрибут com)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.restricted
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
ms.openlocfilehash: a47c56673e19f891b24ff433b9c614804f0bd51c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166371"
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

*интерфейс*<br/>
Один или несколько интерфейсов, которые не могут вызываться произвольно для COM-объекта. Этот параметр допустим только при применении к классу.

## <a name="remarks"></a>Remarks

Атрибут **restrict** C++ имеет те же функциональные возможности, что и атрибут [ограниченного](/windows/win32/Midl/restricted) MIDL.

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
|**Применение**|Метод интерфейса, **интерфейс**, **класс**, **Структура**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|**coclass** (при применении к **классу** или **структуре**)|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)
