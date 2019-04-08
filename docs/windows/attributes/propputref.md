---
title: propputref (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propputref
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
ms.openlocfilehash: e471e467c55e0b8a17be96fd1bcb3cd24cfafe06
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031833"
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

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)