---
title: custom (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 185517720af7e61f6a04068e8868d258a51f262f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215326"
---
# <a name="custom-c"></a>custom (C++)

Определяет метаданные для объекта в библиотеке типов.

## <a name="syntax"></a>Синтаксис

```cpp
[ custom(
   uuid,
   value
) ];
```

### <a name="parameters"></a>Параметры

*uuid*<br/>
Уникальный идентификатор.

*value*<br/>
Значение, которое может быть помещается в вариант.

## <a name="remarks"></a>Remarks

**Настраиваемый** атрибут C++ приведет к помещению данных в библиотеку типов. Вам потребуется средство, считывающее пользовательское значение из библиотеки типов.

**Пользовательский** атрибут имеет те же функциональные возможности, что и [Пользовательский](/windows/win32/Midl/custom) атрибут MIDL.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Не com- **интерфейс**, **`class`** , **`enum`** s, `idl_module` методы, члены интерфейса, параметры интерфейса, s, **`typedef`** **`union`** **`struct`** s|
|**REPEATABLE**|Да|
|**Требуемые атрибуты**|**coclass** (при использовании в классе)|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)
