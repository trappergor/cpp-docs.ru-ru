---
title: propget | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 17c5742fccdc32396b36d058188f3609caf08791
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586750"
---
# <a name="propget"></a>propget

Указывает функции метода доступа свойства.

## <a name="syntax"></a>Синтаксис

```cpp
[propget]
```

## <a name="remarks"></a>Примечания

**Propget** атрибут C++ имеет ту же функциональность, что [propget](http://msdn.microsoft.com/library/windows/desktop/aa367145) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [bindable](../windows/bindable.md) использовать образец **propget**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`propput`, `propputref`|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[propput](../windows/propput.md)  
[propputref](../windows/propputref.md)  