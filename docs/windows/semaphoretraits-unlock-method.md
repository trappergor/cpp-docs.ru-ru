---
title: "Метод SemaphoreTraits::Unlock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
dev_langs: C++
helpviewer_keywords: Unlock method
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 819f7d7e4e4d5b6182da6172bd91a1e799379b52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="semaphoretraitsunlock-method"></a>Метод SemaphoreTraits::Unlock
Элемент управления выпуски общего ресурса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Дескриптор объекта семафора.  
  
## <a name="remarks"></a>Примечания  
 Если операция разблокирования завершается неудачно, Unlock() выдает ошибку, которые указывают на причину сбоя.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Структура SemaphoreTraits](../windows/semaphoretraits-structure.md)