---
title: Метод SemaphoreTraits::Unlock | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0914c6ff83e881f92963fc8a548ddeff587db75e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892251"
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