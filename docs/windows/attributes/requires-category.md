---
title: requires_category (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requires_category
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
ms.openlocfilehash: ec35a1958d9fbcf77fef7f498c6c0dba3ab17df9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022143"
---
# <a name="requirescategory"></a>requires_category

Указывает необходимый компонент категории целевого класса.

## <a name="syntax"></a>Синтаксис

```cpp
[ requires_category(
  requires_category) ]
```

### <a name="parameters"></a>Параметры

*requires_category*<br/>
Идентификатор необходимая категория.

## <a name="remarks"></a>Примечания

**Requires_category** C++ атрибут задает категории компонентов, требуемых для целевого класса. Дополнительные сведения см. в разделе [REQUIRED_CATEGORY](../../atl/reference/category-macros.md#required_category).

Этот атрибут требует, чтобы атрибут [coclass](coclass.md), [progid](progid.md)или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу.

## <a name="example"></a>Пример

Следующий код требует, что объект реализует категорию элемента управления.

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
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Один или несколько из следующих: `coclass`, `progid`, или `vi_progid`.|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты COM](com-attributes.md)<br/>
[implements_category](implements-category.md)