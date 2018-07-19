---
title: support_error_info | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.support_error_info
dev_langs:
- C++
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c366a379d15e50aabdc3c2157f57f85b6b5b33b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889934"
---
# <a name="supporterrorinfo"></a>support_error_info
Реализует поддержку для возвращения подробных сведений об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ support_error_info(  
   error_interface=uuid  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 **error_interface**  
 Идентификатор для реализации интерфейса **IErrorInfo**.  
  
## <a name="remarks"></a>Примечания  
 Атрибут **support_error_info** языка C++ реализует поддержку для возвращения на клиент подробных контекстных ошибок, обнаруженных для целевого объекта. Чтобы объект поддерживал ошибки, он должен реализовывать методы интерфейса **IErrorInfo** . Дополнительные сведения см. в разделе [Supporting IDispatch and IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)(Поддержка IDispatch и IErrorInfo).  
  
 Этот атрибут добавляет [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) в качестве базового класса для целевого объекта. Это приведет к реализация по умолчанию **ISupportErrorInfo** и может использоваться, когда отдельный интерфейс выдает ошибки для объекта.  
  
## <a name="example"></a>Пример  
 Следующий код добавляет поддержку по умолчанию интерфейса **ISupportErrorInfo** в объект `CMyClass` .  
  
```  
// cpp_attr_ref_support_error_info.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="mymod")];  
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]  
__interface IMyErrors  
{  
};  
  
[ coclass, support_error_info("IMyErrors"),  
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]  
class CMyClass  
{  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**|  
|**Повторяемый**|Да|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты COM](../windows/com-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
