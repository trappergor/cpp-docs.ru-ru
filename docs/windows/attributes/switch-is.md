---
title: switch_is (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_is
helpviewer_keywords:
- switch_is attribute
ms.assetid: f1fffe5d-12d2-4e0f-8803-ccb715177d2d
ms.openlocfilehash: 85ee066a12d4297d9a782ae07ef0fa16798f1616
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228054"
---
# <a name="switch_is"></a>switch_is

Указывает выражение или идентификатор, выступающий в качестве discriminant объединения, который выбирает элемент объединения.

## <a name="syntax"></a>Синтаксис

```cpp
[switch_is]
```

## <a name="remarks"></a>Remarks

Атрибут **switch_is** C++ имеет те же функциональные возможности, что и атрибут [switch_is](/windows/win32/Midl/switch-is) MIDL.

## <a name="example"></a>Пример

Пример использования **switch_is**см. в примере [варианта](case-cpp.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**`typedef`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также статью

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[switch_type](switch-type.md)
