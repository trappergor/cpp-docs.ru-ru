---
title: Необязательный (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.optional
helpviewer_keywords:
- optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
ms.openlocfilehash: bc6422ff652cfaba5fa71285294b93c1f0e8990e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032944"
---
# <a name="optional-c"></a>optional (C++)

Задает необязательный параметр для функции-члена.

## <a name="syntax"></a>Синтаксис

```cpp
[optional]
```

## <a name="remarks"></a>Примечания

**Необязательно** атрибут C++ имеет ту же функциональность, что [необязательно](/windows/desktop/Midl/optional) описании атрибута MIDL.

## <a name="example"></a>Пример

В следующем коде показано, как **необязательно** может использоваться:

```cpp
// cpp_attr_ref_optional.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)