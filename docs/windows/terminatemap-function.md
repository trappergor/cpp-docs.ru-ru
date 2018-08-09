---
title: Функция TerminateMap | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d33cbd46903a37bf42e417a100d26c9b706058c0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645942"
---
# <a name="terminatemap-function"></a>Функция TerminateMap
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
### <a name="parameters"></a>Параметры  
 *модуль*  
 Объект [модуль](../windows/module-class.md).  
  
 *Имя_сервера*  
 Имя подмножества фабрик классов в модуль, указанный параметром *модуль*.  
  
 *forceTerminate*  
 **значение true,** завершить класс фабрик, независимо от того, они активны; **false** чтобы не завершать работу фабрик классов, если какая-либо активен.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если всех фабрик классов была завершена; в противном случае — значение **false**.  
  
## <a name="remarks"></a>Примечания  
 Завершает работу фабрик классов в указанном модуле.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)