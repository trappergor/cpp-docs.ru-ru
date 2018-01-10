---
title: "requires_category | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.requires_category
dev_langs: C++
helpviewer_keywords: requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 677e3c94a5db69dafb66a5cd33749c129cb35afb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="requirescategory"></a>requires_category
Задает категории обязательный компонент целевого класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
     [ requires_category(   
  requires_category  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *requires_category*  
 Идентификатор необходимая категория.  
  
## <a name="remarks"></a>Примечания  
 **Requires_category** C++ атрибут задает категории компонентов, предусмотренного для целевого класса. Дополнительные сведения см. в разделе [REQUIRED_CATEGORY](../atl/reference/category-macros.md#required_category).  
  
 Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../windows/progid.md)или [vi_progid](../windows/vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу.  
  
## <a name="example"></a>Пример  
 Следующий код требует, чтобы объект реализован категорию элемента управления.  
  
```  
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
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Один или несколько из следующих: **coclass**, **progid**или **vi_progid**.|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты COM](../windows/com-attributes.md)   
 [implements_category](../windows/implements-category.md)   
