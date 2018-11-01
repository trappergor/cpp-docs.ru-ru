---
title: max_is (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.max_is
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
ms.openlocfilehash: 10732d5ba3251185dc7027e3449486af3037f763
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627478"
---
# <a name="maxis"></a>max_is

Определяет максимальное значение для индекса допустимым массивом.

## <a name="syntax"></a>Синтаксис

```cpp
[ max_is("expression") ]
```

### <a name="parameters"></a>Параметры

*Выражение*<br/>
Одно или несколько выражений языка. Допускаются слотов пустой аргумент.

## <a name="remarks"></a>Примечания

**Max_is** атрибут C++ имеет ту же функциональность, что [max_is](/windows/desktop/Midl/max-is) описании атрибута MIDL.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В поле **структуры** или **объединение**, параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|**size_is**|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Пример

См. в разделе [first_is](first-is.md) пример указания фрагмент массива.

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)