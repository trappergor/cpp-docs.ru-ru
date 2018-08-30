---
title: Глобальные функции контекста устройства | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8944ecdb4f9996800264986a7a687df6020b0591
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209937"
---
# <a name="device-context-global-functions"></a>Глобальные функции контекста устройства
Эта функция создает контекст устройства для данного устройства.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Создает контекст устройства.|  
  
##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC  
 Создает контекст устройства для устройства, заданного в [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) структуры.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>Параметры  
 *hdc*  
 [in] Существующий дескриптор контекста устройства, или значение NULL.  
  
 *ptd*  
 [in] Указатель на `DVTARGETDEVICE` структуру, содержащую сведения о целевом устройстве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор контекста устройства для устройства, заданного в `DVTARGETDEVICE`. Если устройство не указано, возвращает дескриптор для устройства отображения по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Если структура имеет значение NULL и *hdc* имеет значение NULL, создает контекст устройства для устройства отображения по умолчанию.  
  
 Если *hdc* не равно NULL и *ptd* имеет значение NULL, функция возвращает существующий *hdc*.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
   
## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
