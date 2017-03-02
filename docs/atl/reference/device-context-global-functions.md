---
title: "Глобальные функции контекста устройства | Документы Microsoft"
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
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8c71781519b965717acbcefab6fe6a183686caef
ms.lasthandoff: 02/24/2017

---
# <a name="device-context-global-functions"></a>Глобальные функции контекста устройства
Эта функция создает контекст устройства для заданного устройства.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Создает контекст устройства.|  
  
##  <a name="a-nameatlcreatetargetdca--atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a>AtlCreateTargetDC  
 Создает контекст устройства для устройства, указанного в [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) структуры.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>Параметры  
 *hdc*  
 [in] Существующий дескриптор контекста устройства, или **NULL**.  
  
 `ptd`  
 [in] Указатель на **DVTARGETDEVICE** структуру, содержащую сведения о целевом устройстве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор контекста устройства для устройства, указанного в **DVTARGETDEVICE**. Если устройство не указано, возвращает дескриптор устройства отображения по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Если структура **NULL** и *hdc* — **NULL**, создает контекст устройства для устройства отображения по умолчанию.  
  
 Если *hdc* не **NULL** и `ptd` — **NULL**, функция возвращает существующий *hdc*.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
   
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)

