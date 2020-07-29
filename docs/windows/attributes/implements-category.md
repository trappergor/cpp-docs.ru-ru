---
title: implements_category (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.implements_category
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
ms.openlocfilehash: 067a3a183820b09112217647e20d12b592540613
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224426"
---
# <a name="implements_category"></a>implements_category

Указывает категории компонентов, реализуемых целевым классом.

## <a name="syntax"></a>Синтаксис

```cpp
[ implements_category(implements_category="uuid") ]
```

### <a name="parameters"></a>Параметры

*implements_category*<br/>
Идентификатор реализованной категории.

## <a name="remarks"></a>Remarks

Атрибут **implements_category** C++ задает категории компонентов, реализуемых целевым классом. Это можно сделать, создав карту категорий и добавив отдельные записи, заданные атрибутом **implements_category** . Дополнительные сведения см. в разделах [категории компонентов и принципы их работы](/windows/win32/com/component-categories-and-how-they-work).

Этот атрибут требует, чтобы атрибут [coclass](coclass.md), [progid](progid.md)или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например, если `progid` применяется, то применяются `vi_progid` `coclass` также и.

## <a name="example"></a>Пример

Следующий код указывает, что следующий объект реализует `Control` категорию.

```cpp
// cpp_attr_ref_implements_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLib")];
[ coclass, implements_category("CATID_Control"),
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]
class CMyClass {};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Да|
|**Требуемые атрибуты**|Один из следующих элементов: `coclass` , `progid` или`vi_progid`|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также статью

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[IMPLEMENTED_CATEGORY](../../atl/reference/category-macros.md#implemented_category)
