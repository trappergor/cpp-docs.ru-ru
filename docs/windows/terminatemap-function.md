---
title: Функция TerminateMap | Документы Microsoft
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
ms.openlocfilehash: b4787fec0a6b4b9f55c500b66786372945d9a523
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890353"
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
  
## <a name="parameters"></a>Параметры  
 `module`  
 Объект [модуль](../windows/module-class.md).  
  
 `serverName`  
 Имя подмножества фабрик классов в модуле, который указан в параметре `module`.  
  
 `forceTerminate`  
 Значение `true`, если требуется завершить работу фабрик классов независимо от их активности; значение  `false`, чтобы не завершать работу фабрик классов, если какая-либо из них активна.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если работа всех фабрик классов была завершена; в противном случае — значение `false`.  
  
## <a name="remarks"></a>Примечания  
 Завершает работу фабрик классов в указанном модуле.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)