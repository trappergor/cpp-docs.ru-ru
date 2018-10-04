---
title: wire_marshal (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.wire_marshal
dev_langs:
- C++
helpviewer_keywords:
- wire_marshal attribute
ms.assetid: 244f9d72-776d-4ebd-b60a-cee600a126b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 599d602eba101a41892ea66cf203ea9d3d740e1e
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792369"
---
# <a name="wiremarshal"></a>wire_marshal

Указывает тип данных, который будет использоваться для передачи данных вместо типа данных приложения.

## <a name="syntax"></a>Синтаксис

```cpp
[wire_marshal]
```

## <a name="remarks"></a>Примечания

**Wire_marshal** атрибут C++ имеет ту же функциональность, что [wire_marshal](/windows/desktop/Midl/wire-marshal) описании атрибута MIDL.

## <a name="example"></a>Пример

В следующем коде показано использование **wire_marshal**:

```cpp
// cpp_attr_ref_wire_marshal.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[export, public] typedef unsigned long _FOUR_BYTE_DATA;

[export] typedef struct _TWO_X_TWO_BYTE_DATA {
   unsigned short low;
   unsigned short high;
} TWO_X_TWO_BYTE_DATA ;

[export, wire_marshal(TWO_X_TWO_BYTE_DATA)] typedef _FOUR_BYTE_DATA FOUR_BYTE_DATA;
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**typedef**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)  