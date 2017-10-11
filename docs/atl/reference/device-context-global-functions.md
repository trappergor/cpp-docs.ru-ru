---
title: "Глобальные функции контекста устройства | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: d2560043bc97c384846696b76d8e38b459ae4a34
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="device-context-global-functions"></a>Глобальные функции контекста устройства
Эта функция создает контекст устройства для данного устройства.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Создает контекст устройства.|  
  
##  <a name="atlcreatetargetdc"></a>AtlCreateTargetDC  
 Создает контекст устройства для устройства, заданного в [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) структуры.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>Параметры  
 *hdc*  
 [in] Существующий дескриптор контекста устройства, или **NULL**.  
  
 `ptd`  
 [in] Указатель на **DVTARGETDEVICE** структуру, содержащую сведения о целевом устройстве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор контекста устройства для устройства, заданного в **DVTARGETDEVICE**. Если устройство не указано, возвращает дескриптор устройства отображения по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Если структура **NULL** и *hdc* — **NULL**, создает контекст устройства для устройства отображения по умолчанию.  
  
 Если *hdc* не **NULL** и `ptd` — **NULL**, функция возвращает существующую *hdc*.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
   
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)

