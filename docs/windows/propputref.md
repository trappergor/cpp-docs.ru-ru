---
title: propputref | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propputref
dev_langs:
- C++
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2afa793371f2e9840bbb98efc9f745ecbdd29b7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389334"
---
# <a name="propputref"></a>propputref

Задает функцию настройки свойства, которая использует ссылку вместо значения.

## <a name="syntax"></a>Синтаксис

```cpp
[propputref]
```

## <a name="remarks"></a>Примечания

**Propputref** атрибут C++ имеет ту же функциональность, что [propputref](/windows/desktop/Midl/propputref) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [bindable](../windows/bindable.md) использовать образец **propputref**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`propget`, `propput`|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты метода](../windows/method-attributes.md)<br/>
[propget](../windows/propget.md)<br/>
[propput](../windows/propput.md)  