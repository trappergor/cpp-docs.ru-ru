---
title: helpstring (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstring
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
ms.openlocfilehash: 18a8dbea2387224070903aa10c812c9dd079bf96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217263"
---
# <a name="helpstring"></a>helpstring

Определяет строку символов, используемую для описания элемента, к которому оно применяется.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpstring("string") ]
```

### <a name="parameters"></a>Параметры

*строка*<br/>
Текст строки справки.

## <a name="remarks"></a>Remarks

Атрибут **helpString** C++ имеет те же функциональные возможности, что и атрибут [helpString](/windows/win32/Midl/helpstring) MIDL.

## <a name="example"></a>Пример

Пример использования **helpString**см. в примере для [DefaultValue](defaultvalue.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**интерфейс**, **`typedef`** , **`class`** , метод, свойство|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpcontext](helpcontext.md)
