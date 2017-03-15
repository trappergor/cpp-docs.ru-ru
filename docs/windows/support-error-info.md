---
title: "support_error_info | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.support_error_info"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "support_error_info - атрибут"
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# support_error_info
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Реализует поддержку для возвращения подробных сведений об ошибках.  
  
## Синтаксис  
  
```  
  
[ support_error_info(  
   error_interface=  
uuid  
) ]  
  
```  
  
#### Параметры  
 **error\_interface**  
 Идентификатор для реализации интерфейса **IErrorInfo**.  
  
## Заметки  
 Атрибут **support\_error\_info** языка C\+\+ реализует поддержку для возвращения на клиент подробных контекстных ошибок, обнаруженных для целевого объекта. Чтобы объект поддерживал ошибки, он должен реализовывать методы интерфейса **IErrorInfo**. Дополнительные сведения см. в разделе [Supporting IDispatch and IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md) \(Поддержка IDispatch и IErrorInfo\).  
  
 Этот атрибут добавляет [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) в качестве базового класса для целевого объекта. Это приведет к реализация по умолчанию **ISupportErrorInfo** и может использоваться, когда отдельный интерфейс выдает ошибки для объекта.  
  
## Пример  
 Следующий код добавляет поддержку по умолчанию интерфейса **ISupportErrorInfo** в объект `CMyClass`.  
  
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
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**|  
|**Повторяемый**|Да|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## См. также  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)