---
title: last_is | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.last_is
dev_langs:
- C++
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b09b6c89a6dccd0b1cc78346838b79aacb7e9200
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594555"
---
# <a name="lastis"></a>last_is

Указывает индекс последнего элемента массива для передачи.

## <a name="syntax"></a>Синтаксис

```cpp
[ last_is(
   "expression"
) ]
```

### <a name="parameters"></a>Параметры

*Выражение*  
Одно или несколько выражений языка. Допускаются слотов пустой аргумент.

## <a name="remarks"></a>Примечания

**Last_is** атрибут C++ имеет ту же функциональность, что [last_is](http://msdn.microsoft.com/library/windows/desktop/aa367066) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [first_is](../windows/first-is.md) пример указания фрагмент массива.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В поле **структуры** или **объединение**, параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)  
[Атрибуты параметра](../windows/parameter-attributes.md)  
[first_is](../windows/first-is.md)  
[max_is](../windows/max-is.md)  
[length_is](../windows/length-is.md)  
[size_is](../windows/size-is.md)  