---
title: size_is (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.size_is
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
ms.openlocfilehash: c511901b3da03d14b1a09e178b70e8f78cd00f8c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166254"
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
|**Применение**|Поле в **структуре** или **объединении**, параметр интерфейса, метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|`max_is`|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)
