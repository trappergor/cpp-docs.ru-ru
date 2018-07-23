---
title: Перечисление ModuleType | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
dev_langs:
- C++
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d36355c9f64f9f5c827ef8c4d5b3cb6a77d17b65
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876840"
---
# <a name="moduletype-enumeration"></a>ModuleType - перечисление
Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
enum ModuleType;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`InProc`|Внутрипроцессный сервер.|  
|`OutOfProc`|Сервер "out of process".|  
|`DisableCaching`|Отключите механизм кэширования для модуля.|  
|`InProcDisableCaching`|Сочетание `InProc` и `DisableCaching`.|  
|`OutOfProcDisableCaching`|Сочетание `OutOfProc` и `DisableCaching`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)