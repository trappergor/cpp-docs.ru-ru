---
title: switch_is (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_is
helpviewer_keywords:
- switch_is attribute
ms.assetid: f1fffe5d-12d2-4e0f-8803-ccb715177d2d
ms.openlocfilehash: b72052f4cbd7f94b170ea58b8f7b284b85d7ab00
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513976"
---
# <a name="switch_is"></a>switch_is

Указывает выражение или идентификатор, выступающий в качестве discriminant объединения, который выбирает элемент объединения.

## <a name="syntax"></a>Синтаксис

```cpp
[switch_is]
```

## <a name="remarks"></a>Примечания

Атрибут **switch_is** C++ имеет те же функциональные возможности, что и атрибут [switch_is](/windows/win32/Midl/switch-is) MIDL.

## <a name="example"></a>Пример

Пример использования **switch_is**см. в примере [варианта](case-cpp.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**typedef**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[switch_type](switch-type.md)