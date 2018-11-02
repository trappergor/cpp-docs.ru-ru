---
title: custom (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 7aca125879591f71fe2ba60f34b712918350940f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565702"
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

*значение*<br/>
Значение, которое можно поместить в тип variant.

## <a name="remarks"></a>Примечания

**Пользовательских** атрибут C++ приведет к сведения, которые нужно поместить в библиотеке типов. Вам потребуется средство, которое считывает пользовательское значение из библиотеки типов.

**Пользовательских** атрибут имеет ту же функциональность, что [пользовательских](/windows/desktop/Midl/custom) описании атрибута MIDL.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|COM не **интерфейс**, **класс**, **перечисления**s, `idl_module` методов, члены интерфейса, параметров интерфейса **typedef**s, **объединение**s, **структуры**s|
|**Повторяемый**|Да|
|**Обязательные атрибуты**|**Компонентный класс** (при использовании класса)|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)