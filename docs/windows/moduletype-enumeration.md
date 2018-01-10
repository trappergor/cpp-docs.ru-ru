---
title: "Перечисление ModuleType | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ModuleType
dev_langs: C++
helpviewer_keywords: ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd68d911a3734510bfb35db4b3ee0c4b8e46a4a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="moduletype-enumeration"></a>ModuleType - перечисление
Указывает, должен ли модуль поддерживать внутрипроцессный или внепроцессный сервер.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
enum ModuleType;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="values"></a>Значения  
  
|Имя|Описание:|  
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