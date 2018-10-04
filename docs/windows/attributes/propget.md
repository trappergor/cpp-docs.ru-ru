---
title: propget (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propget
dev_langs:
- C++
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 44a5b06a4d94bc431d33fa29cdcef4738e43ca54
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792400"
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

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[propput](propput.md)<br/>
[propputref](propputref.md)  