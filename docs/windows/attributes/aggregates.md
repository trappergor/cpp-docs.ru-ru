---
title: статистические выраженияC++ (атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.aggregates
helpviewer_keywords:
- aggregates attribute
- aggregation [C++]
- aggregate objects [C++], aggregates attribute
- aggregates [C++]
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
ms.openlocfilehash: c9e3f84fbc781bd5187ae0c3461a6c8d68a29aa0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501885"
---
# <a name="aggregates"></a>статистические выражения

Указывает, что объект выполняет статистическое вычисление объекта, заданного параметром CLSID.

## <a name="syntax"></a>Синтаксис

```cpp
[ aggregates(clsid, variable_name) ]
```

### <a name="parameters"></a>Параметры

*этому*<br/>
Указывает CLSID статистически вычисляемого объекта.

*variable_name*<br/>
Имя переменной для вставки. Эта переменная содержит `IUnknown` коллекцию объектов, для которых выполняется статистическая обработка.

## <a name="remarks"></a>Примечания

При применении к объекту атрибут **aggregates** языка C++ реализует внешнюю программу-оболочку статистически вычисляемого объекта (указан в `clsid`).

Этот атрибут требует, чтобы атрибут [coclass](coclass.md), [progid](progid.md)или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например, если `progid` применяется, `vi_progid` то применяются также `coclass` и.

### <a name="atl-projects"></a>Проекты ATL

Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. Во-первых, в карту COM целевого объекта добавляется следующая запись:

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)
```

Во-вторых, также добавляется макрос [DECLARE_GET_CONTROLLING_UNKNOWN](../../atl/reference/aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) .

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_aggregates.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

// requires 'aggregatable.dll'
// see aggregatable attribute to create 'aggregatable.dll'
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;

[module (name="MYObject")];
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]
__interface IObject
{
};

[ coclass, aggregates(__uuidof(CMyClass)),
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]
struct CObject : IObject
{
   int i;
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**класс**, **Структура**|
|**Повторяемый**|Да|
|**Обязательные атрибуты**|Один или несколько из следующих элементов: `coclass`, `progid`или `vi_progid`.|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Статистическая обработка](/windows/win32/com/aggregation)<br/>
[Статистически](/windows/win32/Midl/aggregatable)<br/>
[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](../../atl/reference/com-interface-entry-macros.md#com_interface_entry_autoaggregate_blind)