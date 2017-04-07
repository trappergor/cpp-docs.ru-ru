---
title: "Класс CComAutoDeleteCriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: eb53a0966d29759bbe7513f6042f72a280801707
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautodeletecriticalsection-class"></a>Класс CComAutoDeleteCriticalSection
Этот класс предоставляет методы для получения и освобождения владельца объекта критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>Примечания  
 `CComAutoDeleteCriticalSection`является производным от класса [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Тем не менее `CComAutoDeleteCriticalSection` переопределяет [термин](ccomsafedeletecriticalsection-class.md#term) метод `private` доступа, что обеспечивает внутреннюю память очистки возникает только в случае экземпляры этого класса выходят за пределы области или удаляется из памяти.  

  
 Этот класс представлен без дополнительных методов базового класса. В разделе [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) и [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) Дополнительные сведения о вспомогательных классов критический раздел.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
## <a name="see-also"></a>См. также  
 [Класс CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

