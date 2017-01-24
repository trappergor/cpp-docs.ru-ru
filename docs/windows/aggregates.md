---
title: "статистические выражения | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.aggregates"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregates - атрибут"
  - "агрегирование [C++]"
  - "агрегатные объекты [C++], атрибут aggregates"
  - "статистические выражения [C++]"
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# статистические выражения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, что объект выполняет статистическое вычисление объекта, заданного параметром CLSID.  
  
## Синтаксис  
  
```  
  
[ aggregates(  
clsid,  
variable_name  
) ]  
  
```  
  
#### Параметры  
 `clsid`  
 Указывает CLSID статистически вычисляемого объекта.  
  
 `variable_name`  
 Имя переменной для вставки. Эта переменная содержит **IUnknown** для статистически вычисляемого объекта.  
  
## Заметки  
 При применении к объекту атрибут **aggregates** языка C\+\+ реализует внешнюю программу\-оболочку статистически вычисляемого объекта \(указан в `clsid`\).  
  
 Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../Topic/progid.md) или [vi\_progid](../windows/vi-progid.md) \(или другой атрибут, который подразумевает один из них\) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если **progid** применяется, **vi\_progid** и **coclass** также применяются.  
  
 **Проекты ATL**  
  
 Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. Во\-первых, в карту COM целевого объекта добавляется следующая запись:  
  
```  
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```  
  
 Во\-вторых, также добавляется макрос [DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md).  
  
## Пример  
  
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
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Да|  
|**Обязательные атрибуты**|Один или несколько из следующих: **coclass**, **progid** или **vi\_progid**.|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## См. также  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Статистическая обработка](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [Aggregatable](http://msdn.microsoft.com/library/windows/desktop/aa366721)   
 [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)