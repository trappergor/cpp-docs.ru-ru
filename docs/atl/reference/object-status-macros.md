---
title: "Объект состояния макросы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs: C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc74d545388199eab2aca63ecdea1fdd62a9ef23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="object-status-macros"></a>Макросы состояния объекта
Этот макрос задает флаги, относящиеся к элементам управления ActiveX.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|Используется в элементах управления ActiveX библиотеки ATL для задания **OLEMISC, ПОЗВОЛЯЯ** флаги.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  

##  <a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS  
 Используется в элементах управления ActiveX библиотеки ATL необходимо установить флаги OLEMISC, ПОЗВОЛЯЯ.  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>Параметры  
 *MiscStatus*  
 Все установленные флаги OLEMISC, ПОЗВОЛЯЯ.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется для задания OLEMISC, ПОЗВОЛЯЯ флаги для элемента управления ActiveX. Ссылаться на [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) для получения дополнительных сведений.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
