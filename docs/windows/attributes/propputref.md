---
title: propputref (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propputref
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
ms.openlocfilehash: 9dc21494886f80890bcfde7f29bb3d6c86b4a51b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514180"
---
# <a name="propputref"></a>propputref

Задает функцию настройки свойства, которая использует ссылку вместо значения.

## <a name="syntax"></a>Синтаксис

```cpp
[propputref]
```

## <a name="remarks"></a>Примечания

Атрибут **propputref** C++ имеет те же функциональные возможности, что и атрибут [propputref](/windows/win32/Midl/propputref) MIDL.

## <a name="example"></a>Пример

Пример использования **propputref**см. в примере для [привязки](bindable.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Метод|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|`propget`, `propput`|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)