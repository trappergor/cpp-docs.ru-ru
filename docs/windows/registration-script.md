---
title: registration_script | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.registration_script
dev_langs:
- C++
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4385dd12fccafb154a637dd5260764667d3887a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878727"
---
# <a name="registrationscript"></a>registration_script
Выполняет указанную регистрацию, пользовательский скрипт.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ registration_script(   
   script   
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *Сценарий*  
 Полный путь к регистрации пользовательского файла скрипта (RGS-). Значение **нет**, такие как `script = "none"`, указывает, что компонентный класс не требует регистрации.  
  
## <a name="remarks"></a>Примечания  
 **Registration_script** атрибута C++ выполняет регистрацию пользовательского скрипта, указанного с **сценарий**. Если этот атрибут не указан, используется стандартный RGS-файл, (содержащий сведения о регистрации компонента). Дополнительные сведения о файлах, .rgs разделе [компонент реестра ATL (регистратор)](../atl/atl-registry-component-registrar.md).  
  
 Этот атрибут требует, чтобы атрибут [coclass](../windows/coclass.md), [progid](../windows/progid.md)или [vi_progid](../windows/vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу.  
  
## <a name="example"></a>Пример  
 Следующий код указывает, что компонент содержит сценарий реестра с именем cpp_attr_ref_registration_script.rgs.  
  
```  
// cpp_attr_ref_registration_script.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="REG")];  
  
[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]  
__interface IFace {};  
  
// requires "cpp_attr_ref_registration_script.rgs"  
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist  
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),  
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]  
class CMyClass:public IFace {};  
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
 [Атрибуты классов](../windows/class-attributes.md)   
 [rdx](../windows/rdx.md)   
