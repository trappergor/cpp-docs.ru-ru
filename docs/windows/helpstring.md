---
title: HelpString | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstring
dev_langs:
- C++
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2892f957cf8937b5b030e7624bf3e39f546a7103
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437616"
---
# <a name="helpstring"></a>helpstring

Определяет строку символов, используемую для описания элемента, к которому оно применяется.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpstring(
   "string"
) ]
```

### <a name="parameters"></a>Параметры

*string*<br/>
Текст строки справки.

## <a name="remarks"></a>Примечания

**Helpstring** атрибут C++ имеет ту же функциональность, что [helpstring](/windows/desktop/Midl/helpstring) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [defaultvalue](../windows/defaultvalue.md) пример демонстрирует использование **helpstring**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**интерфейс**, **typedef**, **класс**, метод, свойство|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты интерфейса](../windows/interface-attributes.md)<br/>
[Атрибуты классов](../windows/class-attributes.md)<br/>
[Атрибуты метода](../windows/method-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](../windows/helpfile.md)<br/>
[helpcontext](../windows/helpcontext.md)  