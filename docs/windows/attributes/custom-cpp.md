---
title: custom (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 7a1d9bd64a28fa7c08477c6011dc0e8236b7bcf6
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87521256"
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

## <a name="remarks"></a>Примечания

**Настраиваемый** атрибут C++ приведет к помещению данных в библиотеку типов. Вам потребуется средство, считывающее пользовательское значение из библиотеки типов.

**Пользовательский** атрибут имеет те же функциональные возможности, что и [Пользовательский](/windows/win32/Midl/custom) атрибут MIDL.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

- **Применимо к**: не com `interface` , `idl_module` методы, члены интерфейса, параметры интерфейса,,,, **`typedef`** **`class`** **`enum`** **`union`** и **`struct`** типы.
- **REPEATABLE**: Да.
- **Обязательные атрибуты**: **coclass** (при использовании в классе).
- **Недопустимые атрибуты**: нет.

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)
