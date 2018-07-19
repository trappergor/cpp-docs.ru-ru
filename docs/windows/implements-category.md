---
title: implements_category | Документы Microsoft
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
ms.openlocfilehash: 6770f8303af63c66f0d1a656c2b36e034cc2be83
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879039"
---
# <a name="implementscategory"></a>implements_category
Задает категории компонентов, реализуемый целевого класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 **implements_category**  
 Идентификатор категории реализовано.  
  
## <a name="remarks"></a>Примечания  
 **Implements_category** C++ атрибут задает категории компонентов, реализуемый целевого класса. Это делается путем создания карты категории и добавления заданные отдельные записи **implements_category** атрибута. Дополнительные сведения см. в разделе [Каковы категории компонентов и как выполнить их рабочих?](http://msdn.microsoft.com/library/windows/desktop/ms694322).  
  
 Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../windows/progid.md)или [vi_progid](../windows/vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если **progid** применяется, **vi_progid** и **coclass** также применяются.  
  
## <a name="example"></a>Пример  
 Следующий код указывает, что следующий объект реализует категорию элемента управления.  
  
```  
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
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Да|  
|**Обязательные атрибуты**|Одно из следующих: **coclass**, **progid**, или **vi_progid**|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты COM](../windows/com-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [IMPLEMENTED_CATEGORY](../atl/reference/category-macros.md#implemented_category)   
 