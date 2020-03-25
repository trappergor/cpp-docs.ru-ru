---
title: ReadOnly (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: 415ad5e33de3132e055e53178e6e65d411f169f3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214608"
---
# <a name="readonly-c"></a>readonly (C++)

Запрещает назначение элементу данных.

## <a name="syntax"></a>Синтаксис

```cpp
[readonly]
```

## <a name="remarks"></a>Remarks

Атрибут **readonly** языка C++ имеет ту же функциональность, что и атрибут [readonly](/windows/win32/Midl/readonly) языка MIDL.

Если вы хотите запретить изменение параметра метода, используйте атрибут [in](in-cpp.md) .

## <a name="example"></a>Пример

В следующем коде показано использование атрибута **readonly** :

```cpp
// cpp_attr_ref_readonly.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]
__interface IFireTabCtrl
{
   [readonly, id(1)] int i();
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)
