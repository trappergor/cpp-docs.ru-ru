---
title: статистическую обработку (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.aggregatable
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
ms.openlocfilehash: 8d5ceb46a124db8c0082495d48e6ee0e21655422
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391001"
---
# <a name="aggregatable"></a>aggregatable

Указывает, что класс поддерживает агрегирование.

## <a name="syntax"></a>Синтаксис

```cpp
[ aggregatable(value) ]
```

### <a name="parameters"></a>Параметры

*value*<br/>
(Необязательно) Параметр, чтобы указать, когда может быть статистически вычислена COM-объекта:

- `never` Невозможно выполнить статистическую обработку COM-объекта.

- `allowed` COM-объекта могут быть созданы напрямую или он может быть статистически вычислена. Это значение по умолчанию.

- `always` COM-объект не может быть создан напрямую и только можно выполнять статистические вычисления. При вызове `CoCreateInstance` для данного объекта, необходимо указать объект статистической обработки `IUnknown` интерфейс (управляющий `IUnknown`).

## <a name="remarks"></a>Примечания

**Статистическую обработку** атрибут C++ имеет ту же функциональность, что [статистическую обработку](/windows/desktop/Midl/aggregatable) описании атрибута MIDL. Это означает, что компилятор пройдет **статистическую обработку** через атрибут для созданного IDL-файла.

Этот атрибут требует, чтобы атрибут [coclass](coclass.md), [progid](progid.md)или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если `progid` применяется, `vi_progid` и `coclass` также применяются.

### <a name="atl-projects"></a>Проекты ATL

Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. В дополнение к описанную выше проблему атрибут также добавляет одно из следующих макросов целевой класс:

|Значение параметра|Вставленный макрос|
|---------------------|--------------------|
|`Never`|[DECLARE_NOT_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|
|`Allowed`|[DECLARE_POLY_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|
|`Always`|[DECLARE_ONLY_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|

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

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Статистическая обработка](/windows/desktop/com/aggregation)