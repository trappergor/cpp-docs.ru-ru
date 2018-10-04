---
title: propputref (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 147b46a3081f842b247ac7a2227bd07bb75d8fe6
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791168"
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

См. в примере [bindable](bindable.md) использовать образец **propputref**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`propget`, `propput`|

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)  