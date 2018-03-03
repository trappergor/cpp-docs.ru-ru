---
title: "статистические выражения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.aggregates
dev_langs:
- C++
helpviewer_keywords:
- aggregates attribute
- aggregation [C++]
- aggregate objects [C++], aggregates attribute
- aggregates [C++]
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f3fc74f10e0b5900030d48b37d1918de8807d152
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="aggregates"></a>статистические выражения
Указывает, что объект выполняет статистическое вычисление объекта, заданного параметром CLSID.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ aggregates(  
   clsid,  
   variable_name  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 `clsid`  
 Указывает CLSID статистически вычисляемого объекта.  
  
 `variable_name`  
 Имя переменной для вставки. Эта переменная содержит **IUnknown** для статистически вычисляемого объекта.  
  
## <a name="remarks"></a>Примечания  
 При применении к объекту атрибут **aggregates** языка C++ реализует внешнюю программу-оболочку статистически вычисляемого объекта (указан в `clsid`).  
  
 Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../windows/progid.md)или [vi_progid](../windows/vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если **progid** применяется, **vi_progid** и **coclass** также применяются.  
  
 **Проекты ATL**  
  
 Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. Во-первых, в карту COM целевого объекта добавляется следующая запись:  
  
```  
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```  
  
 Во-вторых, также добавляется макрос [DECLARE_GET_CONTROLLING_UNKNOWN](../atl/reference/aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) .  
  
## <a name="example"></a>Пример  
  
```  
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
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Да|  
|**Обязательные атрибуты**|Один или несколько из следующих: **coclass**, **progid**или **vi_progid**.|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты COM](../windows/com-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Агрегат](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [Статистическую обработку](http://msdn.microsoft.com/library/windows/desktop/aa366721)   
 [COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](../atl/reference/com-interface-entry-macros.md#com_interface_entry_autoaggregate_blind)   
 