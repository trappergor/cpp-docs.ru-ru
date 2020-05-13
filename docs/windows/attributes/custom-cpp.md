---
title: custom (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: f51b0210fff4db5be359fa94237f4d7c77b4fef2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214894"
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

**Настраиваемый** C++ атрибут приведет к помещению данных в библиотеку типов. Вам потребуется средство, считывающее пользовательское значение из библиотеки типов.

**Пользовательский** атрибут имеет те же функциональные возможности, что и [Пользовательский](/windows/win32/Midl/custom) атрибут MIDL.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Неcom- **интерфейс**, **класс**, **перечисление**, `idl_module` методы, члены интерфейса, параметры интерфейса, **typedef**s, **Union**s, **Структура**s|
|**Повторяемый**|Да|
|**Обязательные атрибуты**|**coclass** (при использовании в классе)|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)
