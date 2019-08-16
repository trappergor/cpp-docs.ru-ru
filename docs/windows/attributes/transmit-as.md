---
title: transmit_as (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.transmit_as
helpviewer_keywords:
- transmit_as attribute
ms.assetid: 53d0b8ab-5b06-423e-83eb-3d01a10424b2
ms.openlocfilehash: 939013e43f08aeda788e468c995f1736cf6b6928
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513911"
---
# <a name="transmit_as"></a>transmit_as

Предписывает компилятору связать представленный тип, управляемый клиентскими и серверными приложениями, с переданным типом.

## <a name="syntax"></a>Синтаксис

```cpp
[ transmit_as(type) ]
```

### <a name="parameters"></a>Параметры

*type*<br/>
Указывает тип данных, передаваемый между клиентом и сервером.

## <a name="remarks"></a>Примечания

Атрибут **transmit_as** C++ имеет те же функциональные возможности, что и атрибут [transmit_as](/windows/win32/Midl/transmit-as) MIDL.

## <a name="example"></a>Пример

В следующем коде показано использование атрибута **transmit_as** :

```cpp
// cpp_attr_ref_transmit_as.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[export] typedef struct _TREE_NODE_TYPE {
unsigned short data;
struct _TREE_NODE_TYPE * left;
struct _TREE_NODE_TYPE * right;
} TREE_NODE_TYPE;

[export] struct PACKED_NODE {
   unsigned short data;   // same as normal node
   int index;   // array index of parent
};

// A left node recursive built array of
// the nodes in the tree.  Can be unpacked with
// that knowledge
[export] typedef struct _TREE_XMIT_TYPE {
   int count;
   [size_is(count)] PACKED_NODE node[];
} TREE_XMIT_TYPE;

[transmit_as(TREE_XMIT_TYPE)] typedef TREE_NODE_TYPE * TREE_TYPE;
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**typedef**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[export](export.md)