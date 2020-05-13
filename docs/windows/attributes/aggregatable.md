---
title: Статистическая обработкаC++ (атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.aggregatable
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
ms.openlocfilehash: d929543f699dcd20471ff9a9b45f54119f82a40a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168529"
---
# <a name="aggregatable"></a>aggregatable

Указывает, что класс поддерживает агрегирование.

## <a name="syntax"></a>Синтаксис

```cpp
[ aggregatable(value) ]
```

### <a name="parameters"></a>Параметры

*value*<br/>
Используемых Параметр, указывающий, когда можно выполнить статистическую обработку объекта COM:

- `never` объект COM не может быть агрегирован.

- `allowed` объект COM можно создать напрямую или выполнить статистическую обработку. Это значение по умолчанию.

- `always` COM-объект не может быть создан напрямую и может быть агрегирован. При вызове `CoCreateInstance` для этого объекта необходимо указать интерфейс `IUnknown` объекта агрегирования (управляющий `IUnknown`).

## <a name="remarks"></a>Remarks

**Статистический** C++ атрибут имеет те же функциональные возможности, что и [статистический](/windows/win32/Midl/aggregatable) атрибут MIDL. Это означает, что компилятор передает **статистически обрабатываемый** атрибут в созданный IDL-файл.

Этот атрибут требует, чтобы атрибут [coclass](coclass.md), [progid](progid.md)или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например, если применяется `progid`, применяются также `vi_progid` и `coclass`.

### <a name="atl-projects"></a>Проекты ATL

Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. В дополнение к описанному выше поведению, атрибут также добавляет в целевой класс один из следующих макросов:

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
|**Применение**|**класс**, **Структура**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|Один или несколько из следующих элементов: `coclass`, `progid`или `vi_progid`.|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Агрегирование](/windows/win32/com/aggregation)
