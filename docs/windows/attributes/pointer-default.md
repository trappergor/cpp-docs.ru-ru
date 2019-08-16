---
title: pointer_default (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: c70c372e5f1c3a9c2f620a1fa3505fb9d0436e79
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514260"
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

## <a name="remarks"></a>Примечания

Атрибут **pointer_default** C++ имеет те же функциональные возможности, что и атрибут [pointer_default](/windows/win32/Midl/pointer-default) MIDL.

## <a name="example"></a>Пример

Пример использования **pointer_default**см. в примере для [DefaultValue](defaultvalue.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)