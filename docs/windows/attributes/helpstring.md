---
title: helpstring (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstring
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
ms.openlocfilehash: 12707dde61013caa1ed9feb1d0daa74cbb7b9d9a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591377"
---
# <a name="helpstring"></a>helpstring

Определяет строку символов, используемую для описания элемента, к которому оно применяется.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpstring("string") ]
```

### <a name="parameters"></a>Параметры

*string*<br/>
Текст строки справки.

## <a name="remarks"></a>Примечания

**Helpstring** атрибут C++ имеет ту же функциональность, что [helpstring](/windows/desktop/Midl/helpstring) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [defaultvalue](defaultvalue.md) пример демонстрирует использование **helpstring**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**интерфейс**, **typedef**, **класс**, метод, свойство|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpcontext](helpcontext.md)