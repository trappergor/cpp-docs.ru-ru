---
title: propget (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propget
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
ms.openlocfilehash: 044562ba870d6e36ddfcec0c7e84253b111a9eea
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514206"
---
# <a name="propget"></a>propget

Задает функцию доступа к свойству.

## <a name="syntax"></a>Синтаксис

```cpp
[propget]
```

## <a name="remarks"></a>Примечания

Атрибут **propget** C++ имеет те же функциональные возможности, что и атрибут MIDL для [propget](/windows/win32/Midl/propget) .

## <a name="example"></a>Пример

См. пример для [привязки](bindable.md) к примеру использования **propget**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Метод|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|`propput`, `propputref`|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[propput](propput.md)<br/>
[propputref](propputref.md)