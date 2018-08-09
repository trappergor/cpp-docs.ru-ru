---
title: Перечисление ModuleType | Документация Майкрософт
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
ms.openlocfilehash: 831f1fbcb2da205fa08286a1fbbbf414e66075d4
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019934"
---
# <a name="moduletype-enumeration"></a>ModuleType - перечисление
Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum ModuleType;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="values"></a>Значения  
  
|Имя|Описание:|  
|----------|-----------------|  
|`InProc`|Внутрипроцессный сервер.|  
|`OutOfProc`|Сервер вне процесса.|  
|`DisableCaching`|Отключите механизм кэширования для модуля.|  
|`InProcDisableCaching`|Сочетание `InProc` и `DisableCaching`.|  
|`OutOfProcDisableCaching`|Сочетание `OutOfProc` и `DisableCaching`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)