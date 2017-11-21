---
title: "support_error_info | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.support_error_info
dev_langs: C++
helpviewer_keywords: support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 308ab8752b6bd77693e40239d92cc62b6f42caf2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
