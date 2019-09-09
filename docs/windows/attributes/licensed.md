---
title: лицензированоC++ (атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.licensed
helpviewer_keywords:
- licensed attribute
ms.assetid: 09cf3b4a-d3f2-43e3-9180-d420333b23bf
ms.openlocfilehash: 0c637f9e3f6d99b9f197474f49a1a9843744f38b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514451"
---
# <a name="licensed"></a>licensed

Указывает, что COM-объект, к которому применяется, имеет лицензию, и его необходимо создать `IClassFactory2`с помощью.

## <a name="syntax"></a>Синтаксис

```cpp
[licensed]
```

## <a name="remarks"></a>Примечания

Атрибут **Licensed** C++ имеет те же функциональные возможности, что и [лицензированный](/windows/win32/Midl/licensed) атрибут MIDL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_licensed.cpp
// compile with: /LD
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {
   HRESULT f();
};

[coclass, version("2.1"), uuid(12345678-1111-2222-3333-123456789012),
licensed, threading(free), progid(some.name)]
class CSample : public IMyI {
public:
   int nSize;
};

[module(name="MyLibrary", version="1.0", helpstring="My Library Block")];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**класс**, **Структура**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|`coclass`|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)