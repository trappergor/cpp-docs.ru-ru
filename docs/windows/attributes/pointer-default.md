---
title: pointer_default (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: 37bd2b16fb7a7c1c186f59897898e08cc73fffae
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022670"
---
# <a name="pointerdefault"></a>pointer_default

Указывает атрибут указатель по умолчанию для всех указателей, за исключением верхнего уровня указателей, которые отображаются в списках параметров.

## <a name="syntax"></a>Синтаксис

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Параметры

*value*<br/>
Значение, описывающее тип указателя: **ptr**, **ref**, или **уникальный**.

## <a name="remarks"></a>Примечания

**Pointer_default** C++ атрибут имеет ту же функциональность, что [pointer_default](/windows/desktop/Midl/pointer-default) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [defaultvalue](defaultvalue.md) использовать образец **pointer_default**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)