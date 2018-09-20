---
title: статистическое вычисление может выполняться | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregatable
dev_langs:
- C++
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e46bcd45040ffb50ec8bbd10d8d583211d0a3316
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400501"
---
# <a name="aggregatable"></a>aggregatable

Указывает, что класс поддерживает агрегирование.

## <a name="syntax"></a>Синтаксис

```cpp
[ aggregatable(
   value
) ]
```

### <a name="parameters"></a>Параметры

*значение*<br/>
(Необязательно) Параметр, чтобы указать, когда может быть статистически вычислена COM-объекта:

- `never` Невозможно выполнить статистическую обработку COM-объекта.

- `allowed` COM-объекта могут быть созданы напрямую или он может быть статистически вычислена. Это значение по умолчанию.

- `always` COM-объект не может быть создан напрямую и только можно выполнять статистические вычисления. При вызове `CoCreateInstance` для данного объекта, необходимо указать объект статистической обработки `IUnknown` интерфейс (управляющий `IUnknown`).

## <a name="remarks"></a>Примечания

**Статистическую обработку** атрибут C++ имеет ту же функциональность, что [статистическую обработку](/windows/desktop/Midl/aggregatable) описании атрибута MIDL. Это означает, что компилятор пройдет **статистическую обработку** через атрибут для созданного IDL-файла.

Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../windows/progid.md)или [vi_progid](../windows/vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если `progid` применяется, `vi_progid` и `coclass` также применяются.

### <a name="atl-projects"></a>Проекты ATL

Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. В дополнение к описанную выше проблему атрибут также добавляет одно из следующих макросов целевой класс:

|Значение параметра|Вставленный макрос|
|---------------------|--------------------|
|`Never`|[DECLARE_NOT_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|
|`Allowed`|[DECLARE_POLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|
|`Always`|[DECLARE_ONLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_aggregatable.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="MyModule")];

[ coclass, aggregatable(allowed),
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]
class CMyClass {};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Один или несколько из следующих: `coclass`, `progid`, или `vi_progid`.|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты классов](../windows/class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[Статистическая обработка](/windows/desktop/com/aggregation)  