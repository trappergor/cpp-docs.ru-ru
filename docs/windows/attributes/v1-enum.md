---
title: v1_enum (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.v1_enum
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
ms.openlocfilehash: 1a189f6f1c5ef9d4ae77df9f1eda3f3671ddaf52
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166111"
---
# <a name="v1_enum"></a>v1_enum

Указывает, что указанный перечисляемый тип передается как 32-разрядная сущность, а не как 16-разрядное значение по умолчанию.

## <a name="syntax"></a>Синтаксис

```cpp
[v1_enum]
```

## <a name="remarks"></a>Remarks

Атрибут **v1_enum** C++ имеет те же функциональные возможности, что и атрибут [v1_enum](/windows/win32/Midl/v1-enum) MIDL.

## <a name="example"></a>Пример

В следующем коде показано использование **v1_enum**.

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
|**Применение**|Перечисляемый тип|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)
