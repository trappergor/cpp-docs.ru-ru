---
title: только для чтения (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: 7eea071b62130c65fbb46ebc8827fc2b428c4c0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407345"
---
# <a name="readonly-c"></a>readonly (C++)

Запрещает назначение элементу данных.

## <a name="syntax"></a>Синтаксис

```cpp
[readonly]
```

## <a name="remarks"></a>Примечания

Атрибут **readonly** языка C++ имеет ту же функциональность, что и атрибут [readonly](/windows/desktop/Midl/readonly) языка MIDL.

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
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)