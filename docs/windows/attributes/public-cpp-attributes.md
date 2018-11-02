---
title: Public (атрибуты C++) (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.public
helpviewer_keywords:
- public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
ms.openlocfilehash: d89df014beae5a62a035c3156b92d3337ecd2c14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579339"
---
# <a name="public-c-attributes"></a>public (атрибуты C++)

Гарантирует, что typedef перейдет в библиотеке типов, даже если нет ссылок из в IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[public]
```

## <a name="remarks"></a>Примечания

**Открытый** атрибут C++ имеет ту же функциональность, что [открытый](/windows/desktop/Midl/public) описании атрибута MIDL.

## <a name="example"></a>Пример

Ниже показано, как использовать **открытый** атрибут:

```cpp
// cpp_attr_ref_public.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, public] typedef long MEMBERID;

[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]
__interface IFireTabCtrl : IDispatch
{
   [id(2)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**typedef**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)