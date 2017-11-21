---
title: "Функция TerminateMap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::TerminateMap
dev_langs: C++
helpviewer_keywords: TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: efe6b143c2fe9a48a008f9005244178b436d170e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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