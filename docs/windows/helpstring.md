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
ms.openlocfilehash: 928f4fe5200d9ea03541976664d472d9e99e1147
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575694"
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

*string*  
Текст строки справки.

## <a name="remarks"></a>Примечания

**Helpstring** атрибут C++ имеет ту же функциональность, что [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) описании атрибута MIDL.

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

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  
[Атрибуты классов](../windows/class-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)  
[helpfile](../windows/helpfile.md)  
[helpcontext](../windows/helpcontext.md)  