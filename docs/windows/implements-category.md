---
title: implements_category | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.implements_category
dev_langs:
- C++
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e566e50cc0fed4b17b085451410a1d0c3f81fb38
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597551"
---
# <a name="implementscategory"></a>implements_category

— Указывает категории компонента, реализуемый целевого класса.

## <a name="syntax"></a>Синтаксис

```cpp
[ implements_category(
   implements_category="uuid"
) ]
```

### <a name="parameters"></a>Параметры

*implements_category*  
Идентификатор реализованного категории.

## <a name="remarks"></a>Примечания

**Implements_category** C++ атрибут задает категории компонентов, реализуемый целевого класса. Это делается путем создания карты категории и добавления отдельных записей, указанных **implements_category** атрибута. Дополнительные сведения см. в разделе [Каковы категорий компонентов и как сделать они работают?](http://msdn.microsoft.com/library/windows/desktop/ms694322).

Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../windows/progid.md)или [vi_progid](../windows/vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если `progid` применяется, `vi_progid` и `coclass` также применяются.

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

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты COM](../windows/com-attributes.md)  
[Атрибуты классов](../windows/class-attributes.md)  
[IMPLEMENTED_CATEGORY](../atl/reference/category-macros.md#implemented_category)  