---
title: "Объект состояния макросы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
caps.latest.revision: 16
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 433a816b19690f22f482f26f6ab70c73ed102673
ms.lasthandoff: 02/24/2017

---
# <a name="object-status-macros"></a>Макросы состояния объекта
Этот макрос устанавливает флаги, относящиеся к элементам управления ActiveX.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|Используется в элементах управления ATL ActiveX для задания **OLEMISC, ПОЗВОЛЯЯ** флаги.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  

##  <a name="a-namedeclareolemiscstatusa--declareolemiscstatus"></a><a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS  
 Используется в элементах управления ATL ActiveX необходимо установить флаги OLEMISC, ПОЗВОЛЯЯ.  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>Параметры  
 *MiscStatus*  
 Все установленные флаги OLEMISC, ПОЗВОЛЯЯ.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос используется для задания OLEMISC, ПОЗВОЛЯЯ флаги для элемента управления ActiveX. Обратитесь к [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) для получения дополнительных сведений.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#124;](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)

