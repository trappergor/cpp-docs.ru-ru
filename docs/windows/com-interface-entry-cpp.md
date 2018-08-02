---
title: COM_INTERFACE_ENTRY (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.com_interface_entry
dev_langs:
- C++
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd6cc88ba01d7cfc5d7d5712ddeaaef0418bb12a
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462788"
---
# <a name="cominterfaceentry-c"></a>com_interface_entry (C++)
Добавляет запись интерфейс в карту COM целевого класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ com_interface_entry(   
  com_interface_entry  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *COM_INTERFACE_ENTRY*  
 Строка, содержащая текст записи. Список возможных значений см. в разделе [Макросы COM_INTERFACE_ENTRY](../atl/reference/com-interface-entry-macros.md).  
  
## <a name="remarks"></a>Примечания  
 **Com_interface_entry** атрибут C++ вставляет unabridged содержимое символьной строки в схему интерфейсов COM целевого объекта. Если атрибут применяется один раз для целевого объекта, запись вставляется в начало существующих схему интерфейсов. Если атрибут применяется несколько раз для одного целевого объекта, записи вставляются в начале схему интерфейсов в порядке их получения.  
  
 Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../windows/progid.md)или [vi_progid](../windows/vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например если `progid` применяется, `vi_progid` и `coclass` также применяются.  
  
 Так как первый случай использования **com_interface_entry** вызывает новый интерфейс для вставки в начале схему интерфейсов. он должен быть один из следующих типов COM_INTERFACE_ENTRY:  
  
-   COM_INTERFACE_ENTRY  
  
-   COM_INTERFACE_ENTRY_IID  
  
-   COM_INTERFACE_ENTRY2  
  
-   COM_INTERFACE_ENTRY2_IID  
  
 Дополнительные случаи использования **com_interface_entry** атрибут можно использовать все поддерживаемые типы COM_INTERFACE_ENTRY.  
  
 Это ограничение является обязательным, так как ATL использует первый элемент в схему интерфейсов с удостоверением `IUnknown`; таким образом, элемент должен быть допустимый интерфейс. Например следующий код является недопустимым, поскольку первая запись в схему интерфейсов не содержит фактический интерфейс COM.  
  
```  
[ coclass, com_interface_entry =  
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"  
]  
   class CMyClass  
   {  
   };  
```  
  
## <a name="example"></a>Пример  
 Следующий код добавляет две записи в существующую карту интерфейс COM объекта `CMyBaseClass`. Первый — это стандартный интерфейс, а второй скрывает `IDebugTest` интерфейс.  
  
```cpp  
// cpp_attr_ref_com_interface_entry.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name ="ldld")];  
  
[ object,  
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]  
__interface IDebugTest{};  
  
[ object,  
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]  
__interface IMyClass{};  
  
[ coclass,  
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),  
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),  
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")  
]  
  
class CMyClass: public IMyClass, public IDebugTest  
{  
};  
```  
  
 Полученная карта объект COM для `CMyBaseClass` выглядит следующим образом:  
  
```  
BEGIN_COM_MAP(CMyClass)  
    COM_INTERFACE_ENTRY (IMyClass)  
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)  
    COM_INTERFACE_ENTRY(IMyClass)  
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)  
    COM_INTERFACE_ENTRY(IDebugTest)  
    COM_INTERFACE_ENTRY(IProvideClassInfo)  
END_COM_MAP()  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**Класс**, **структуры**|  
|**Повторяемый**|Да|  
|**Обязательные атрибуты**|Один или несколько из следующих: **coclass**, **progid**или **vi_progid**.|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты COM](../windows/com-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)   