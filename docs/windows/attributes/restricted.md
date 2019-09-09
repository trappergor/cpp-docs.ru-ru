---
title: Restricted (C++ атрибут com)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.restricted
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
ms.openlocfilehash: 01dabcd15eb1a14734c16b9e54c0ab2e030d0479
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514061"
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

*interfaces*<br/>
Один или несколько интерфейсов, которые не могут вызываться произвольно для COM-объекта. Этот параметр допустим только при применении к классу.

## <a name="remarks"></a>Примечания

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
|**Относится к**|Метод интерфейса, **интерфейс**, **класс**, **Структура**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**coclass** (при применении к **классу** или **структуре**)|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)