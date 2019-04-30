---
title: implements_category (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.implements_category
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
ms.openlocfilehash: beca804fae8d6e82b4664102b39d76a23e66ca59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409412"
---
# <a name="implementscategory"></a>implements_category

— Указывает категории компонента, реализуемый целевого класса.

## <a name="syntax"></a>Синтаксис

```cpp
[ implements_category(implements_category="uuid") ]
```

### <a name="parameters"></a>Параметры

*implements_category*<br/>
Идентификатор реализованного категории.

## <a name="remarks"></a>Примечания

**Implements_category** C++ атрибут задает категории компонентов, реализуемый целевого класса. Это делается путем создания карты категории и добавления отдельных записей, указанных **implements_category** атрибута. Дополнительные сведения см. в разделе [Каковы категорий компонентов и как сделать они работают?](https://msdn.microsoft.com/library/windows/desktop/ms694322).

Этот атрибут требует, чтобы атрибут [coclass](coclass.md), [progid](progid.md)или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если `progid` применяется, `vi_progid` и `coclass` также применяются.

## <a name="example"></a>Пример

Следующий код указывает, что следующий объект реализует `Control` категории.

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
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Да|
|**Обязательные атрибуты**|Одно из следующих: `coclass`, `progid`, или `vi_progid`|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[IMPLEMENTED_CATEGORY](../../atl/reference/category-macros.md#implemented_category)