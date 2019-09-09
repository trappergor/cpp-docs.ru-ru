---
title: oleautomation (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.oleautomation
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
ms.openlocfilehash: 56970d8b1067e1ac38230b6995074210ddc5549b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514363"
---
# <a name="oleautomation"></a>oleautomation

Указывает, что интерфейс совместим с автоматизацией.

## <a name="syntax"></a>Синтаксис

```cpp
[oleautomation]
```

## <a name="remarks"></a>Примечания

Атрибут **oleautomation** C++ имеет те же функциональные возможности, что и атрибут [oleautomation](/windows/win32/Midl/oleautomation) MIDL.

## <a name="example"></a>Пример

Пример использования **oleautomation**см. в примерах значений [DefaultValue](defaultvalue.md) и [unextensible](nonextensible.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|**dispinterface**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)