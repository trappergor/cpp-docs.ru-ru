---
title: "Структура MutexTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
dev_langs: C++
helpviewer_keywords: MutexTraits structure
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd8dac513b5eec049fbb739ab79628d9f41c96b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mutextraits-structure"></a>MutexTraits - структура
Определяет общие характеристики [мьютекс](../windows/mutex-class1.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct MutexTraits : HANDLENullTraits;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод MutexTraits::Unlock](../windows/mutextraits-unlock-method.md)|Освобождает исключительный контроль общего ресурса.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)