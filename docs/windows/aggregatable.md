---
title: статистическую обработку | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregatable
dev_langs:
- C++
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1d80b2fb707145f698e8d9bb883059478c3da10b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863830"
---
# <a name="aggregatable"></a>aggregatable
Указывает, что класс поддерживает агрегирование.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ aggregatable(   
   value  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *значение* (необязательно)  
 Параметр, чтобы указать, когда может быть статистически вычислена COM-объекта:  
  
-   **никогда не** COM-объект невозможно выполнить статистическую обработку.  
  
-   **Допускается** COM-объект можно создать напрямую, или могут быть агрегированными. Это значение по умолчанию.  
  
-   **всегда** COM-объект нельзя создать напрямую и только могут быть агрегированными. При вызове `CoCreateInstance` для этого объекта необходимо указать статистической обработки объекта **IUnknown** интерфейса (Управление **IUnknown**).  
  
## <a name="remarks"></a>Примечания  
 **Статистическую обработку** языка C++ имеет ту же функциональность, что [статистическую обработку](http://msdn.microsoft.com/library/windows/desktop/aa366721) языка MIDL. Это означает, что компилятор пройдет **статистическую обработку** атрибут через созданного IDL-файла.  
  
 Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../windows/progid.md)или [vi_progid](../windows/vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если **progid** применяется, **vi_progid** и **coclass** также применяются.  
  
 **Проекты ATL**  
  
 Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. Помимо описанную выше проблему атрибут также добавляет одно из следующих макросов целевого класса.  
  
|Значение параметра|Вставленные макрос|  
|---------------------|--------------------|  
|**Никогда не**|[DECLARE_NOT_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|  
|**Допускается**|[DECLARE_POLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|  
|**Всегда**|[DECLARE_ONLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|  
  
## <a name="example"></a>Пример  
  
```  
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
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Один или несколько из следующих: **coclass**, **progid**или **vi_progid**.|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Статистическая обработка](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
