---
title: v1_enum (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.v1_enum
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
ms.openlocfilehash: 08654eed7ad467dc22d2cbbf811c9169e5292f16
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024573"
---
# <a name="v1enum"></a>v1_enum

Указывает, что заданного перечислимого типа, передаваться в объект 32-разрядной, а не по умолчанию 16-разрядное.

## <a name="syntax"></a>Синтаксис

```cpp
[v1_enum]
```

## <a name="remarks"></a>Примечания

**V1_enum** C++ атрибут имеет ту же функциональность, что [v1_enum](/windows/desktop/Midl/v1-enum) описании атрибута MIDL.

## <a name="example"></a>Пример

В следующем коде показано использование **v1_enum**:

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1, e2 = 2
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Перечислимый тип|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)