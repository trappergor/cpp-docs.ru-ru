---
title: propget (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propget
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
ms.openlocfilehash: 8f60e8e8fc98ba3b75acefe80812069bfac78e6c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027302"
---
# <a name="propget"></a>propget

Указывает функции метода доступа свойства.

## <a name="syntax"></a>Синтаксис

```cpp
[propget]
```

## <a name="remarks"></a>Примечания

**Propget** атрибут C++ имеет ту же функциональность, что [propget](/windows/desktop/Midl/propget) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [bindable](bindable.md) использовать образец **propget**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`propput`, `propputref`|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[propput](propput.md)<br/>
[propputref](propputref.md)