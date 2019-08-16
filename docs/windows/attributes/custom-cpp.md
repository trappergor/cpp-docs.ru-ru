---
title: custom (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 19f28963a18abf42c6f629ac0f6491628387aa6d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491003"
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

**Настраиваемый** C++ атрибут приведет к помещению данных в библиотеку типов. Вам потребуется средство, считывающее пользовательское значение из библиотеки типов.

**Пользовательский** атрибут имеет те же функциональные возможности, что и [Пользовательский](/windows/win32/Midl/custom) атрибут MIDL.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Неcom- **интерфейс**, **класс**,перечисление `idl_module` , методы, члены интерфейса, параметры интерфейса, **typedef**s, **объединение**s, **Структура**s|
|**Повторяемый**|Да|
|**Обязательные атрибуты**|**coclass** (при использовании в классе)|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)