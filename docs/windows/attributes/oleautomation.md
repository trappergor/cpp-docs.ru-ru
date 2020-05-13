---
title: oleautomation (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.oleautomation
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
ms.openlocfilehash: 201916eeb235d48473d21188da42d19cafb93bce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214700"
---
# <a name="oleautomation"></a>oleautomation

Указывает, что интерфейс совместим с автоматизацией.

## <a name="syntax"></a>Синтаксис

```cpp
[oleautomation]
```

## <a name="remarks"></a>Remarks

Атрибут **oleautomation** C++ имеет те же функциональные возможности, что и атрибут [oleautomation](/windows/win32/Midl/oleautomation) MIDL.

## <a name="example"></a>Пример

Пример использования **oleautomation**см. в примерах значений [DefaultValue](defaultvalue.md) и [unextensible](nonextensible.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|**dispinterface**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)
