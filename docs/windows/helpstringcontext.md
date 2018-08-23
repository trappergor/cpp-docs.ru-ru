---
title: helpstringcontext | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringcontext
dev_langs:
- C++
helpviewer_keywords:
- helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 34aed4325d2e946f59a4f17275d6b0aabe4de06c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589977"
---
# <a name="helpstringcontext"></a>helpstringcontext

Указывает идентификатор раздела справки в файл с расширением .hlp или .chm.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpstringcontext(
   contextID
) ]
```

### <a name="parameters"></a>Параметры

*contextID*  
В 32-разрядный идентификатор контекста справки в **помочь** файл.

## <a name="remarks"></a>Примечания

**Helpstringcontext** атрибут C++ имеет ту же функциональность, что [helpstringcontext](http://msdn.microsoft.com/library/windows/desktop/aa366858) ODL-атрибут.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_helpstringcontext.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[   object,
   helpstring("help string"),
   helpstringcontext(1),
   uuid="11111111-1111-1111-1111-111111111111"
]
__interface IMyI
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **интерфейс**, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  
[Атрибуты классов](../windows/class-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[модуль](../windows/module-cpp.md)  