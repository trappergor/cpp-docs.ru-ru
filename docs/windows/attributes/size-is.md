---
title: size_is (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.size_is
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
ms.openlocfilehash: 36b960982d1f88cd30bab707dfe7aec73381dfab
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213844"
---
# <a name="size_is"></a>size_is

Укажите размер памяти, выделенной для указателей размера, размеры указателей для указателей размеров, а также однокомпонентные или многомерные массивы.

## <a name="syntax"></a>Синтаксис

```cpp
[ size_is("expression") ]
```

### <a name="parameters"></a>Параметры

*expression*<br/>
Размер памяти, выделенной для указателей размера.

## <a name="remarks"></a>Remarks

Атрибут **size_is** C++ имеет те же функциональные возможности, что и атрибут [size_is](/windows/win32/Midl/size-is) MIDL.

## <a name="example"></a>Пример

Пример указания раздела массива см. в примере для [first_is](first-is.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Поле в **`struct`** или **`union`** , параметр интерфейса, метод интерфейса|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|`max_is`|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)
