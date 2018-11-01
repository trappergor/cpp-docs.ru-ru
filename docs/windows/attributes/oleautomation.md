---
title: oleautomation (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.oleautomation
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
ms.openlocfilehash: 4a50121e1a2e170ba69ee21526f4600512097c74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471673"
---
# <a name="oleautomation"></a>oleautomation

Указывает, что интерфейс совместим со службой автоматизации.

## <a name="syntax"></a>Синтаксис

```cpp
[oleautomation]
```

## <a name="remarks"></a>Примечания

**Oleautomation** атрибут C++ имеет ту же функциональность, что [oleautomation](/windows/desktop/Midl/oleautomation) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примерах [defaultvalue](defaultvalue.md) и [nonextensible](nonextensible.md) использовать образец **oleautomation**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|**dispinterface**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)