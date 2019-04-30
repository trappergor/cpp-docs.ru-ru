---
title: helpstring (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstring
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
ms.openlocfilehash: 623b2c7fb4ce7c3e5de87d21f012d008720fdee2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409594"
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