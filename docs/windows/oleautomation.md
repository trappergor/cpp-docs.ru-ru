---
title: oleautomation | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.oleautomation
dev_langs:
- C++
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e321f8039cbb51dda8cc9103601bd91218f1cdab
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419448"
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

См. в примерах [defaultvalue](../windows/defaultvalue.md) и [nonextensible](../windows/nonextensible.md) использовать образец **oleautomation**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|**dispinterface**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты интерфейса](../windows/interface-attributes.md)  