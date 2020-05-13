---
title: pointer_default (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: d0c5832623c1e418f4c6e8bdb606d1d363503483
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166540"
---
# <a name="pointer_default"></a>pointer_default

Задает атрибут указателя по умолчанию для всех указателей, за исключением указателей верхнего уровня, которые отображаются в списках параметров.

## <a name="syntax"></a>Синтаксис

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Параметры

*value*<br/>
Значение типа, описывающее тип указателя: **ptr**, **ref**или **UNIQUE**.

## <a name="remarks"></a>Remarks

Атрибут **pointer_default** C++ имеет те же функциональные возможности, что и атрибут [pointer_default](/windows/win32/Midl/pointer-default) MIDL.

## <a name="example"></a>Пример

См. пример для [DefaultValue](defaultvalue.md) для примера использования **pointer_default**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)
