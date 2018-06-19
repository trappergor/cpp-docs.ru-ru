---
title: Класс CComAutoDeleteCriticalSection | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5153520b5a5648f8352465031264c223ffd97c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360068"
---
# <a name="ccomautodeletecriticalsection-class"></a>Класс CComAutoDeleteCriticalSection
Этот класс предоставляет методы для получения и освобождения владения объект критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>Примечания  
 `CComAutoDeleteCriticalSection` является производным от класса [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Тем не менее `CComAutoDeleteCriticalSection` переопределяет [термин](ccomsafedeletecriticalsection-class.md#term) метод `private` доступ, который обеспечивает внутреннюю память очистки возникает только в случае экземпляры этого класса выходят за пределы области или удаляется из памяти.  

  
 Этот класс предоставляет дополнительные методы не через своего базового класса. В разделе [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) и [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) Дополнительные сведения о вспомогательных классов критической секции.  
  
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
