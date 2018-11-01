---
title: size_is (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.size_is
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
ms.openlocfilehash: 95b0e16e5f5d085e526f45e8e98898474fc5a17f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449443"
---
# <a name="sizeis"></a>size_is

Укажите объем памяти, выделенной для размера указатели, размер указателей на указатели по размеру и одно - или многомерные массивы.

## <a name="syntax"></a>Синтаксис

```cpp
[ size_is("expression") ]
```

### <a name="parameters"></a>Параметры

*Выражение*<br/>
Размер памяти, выделенной для размера указателей.

## <a name="remarks"></a>Примечания

**Size_is** атрибут C++ имеет ту же функциональность, что [size_is](/windows/desktop/Midl/size-is) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [first_is](first-is.md) пример указания фрагмент массива.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В поле **структуры** или **объединение**, параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`max_is`|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)