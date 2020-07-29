---
title: requires_category (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requires_category
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
ms.openlocfilehash: 044f868a6be8391a4b0dfafd58ff0f3178575047
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231563"
---
# <a name="requires_category"></a>requires_category

Указывает обязательные категории компонентов целевого класса.

## <a name="syntax"></a>Синтаксис

```cpp
[ requires_category(
  requires_category) ]
```

### <a name="parameters"></a>Параметры

*requires_category*<br/>
ИДЕНТИФИКАТОР требуемой категории.

## <a name="remarks"></a>Remarks

Атрибут **requires_category** C++ задает категории компонентов, необходимые для целевого класса. Дополнительные сведения см. в разделе [REQUIRED_CATEGORY](../../atl/reference/category-macros.md#required_category).

Этот атрибут требует, чтобы атрибут [coclass](coclass.md), [progid](progid.md)или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу.

## <a name="example"></a>Пример

В следующем коде требуется, чтобы объект реализовал категорию элемента управления.

```cpp
// cpp_attr_ref_requires_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLibrary")];

[ coclass, requires_category("CATID_Control"),
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]
class CMyClass {};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Один или несколько из следующих элементов: `coclass` , `progid` или `vi_progid` .|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты COM](com-attributes.md)<br/>
[implements_category](implements-category.md)
