---
title: ms_union (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ms_union
helpviewer_keywords:
- ms_union attribute
ms.assetid: bb548689-6962-457e-af56-8ffdf68987eb
ms.openlocfilehash: 3f83eeff4fd9b2177b862b101b7a2d4faeaaab87
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022312"
---
# <a name="msunion"></a>ms_union

Управляет выравниванием представление данных сети nonencapsulated объединений.

## <a name="syntax"></a>Синтаксис

```cpp
[ms_union]
```

## <a name="remarks"></a>Примечания

**Ms_union** атрибут C++ имеет ту же функциональность, что [ms_union](/windows/desktop/Midl/ms-union-attrib) описании атрибута MIDL.

## <a name="example"></a>Пример

В следующем коде показано размещение **ms_union**:

```cpp
// cpp_attr_ref_ms_union.cpp
// compile with: /LD
#include <unknwn.h>
[object, ms_union, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl {
   HRESULT DisplayString([in, string] char * p1);
};

[export, switch_type(short)] union _WILLIE_UNION_TYPE  {
   [case(24)]
      float fMays;
   [case(25)]
      double dMcCovey;
   [default]
      int x;
};

[public] typedef _WILLIE_UNION_TYPE WILLIE_UNION_TYPE;

[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Nonencapsulated объединения|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`dispinterface`|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)