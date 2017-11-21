---
title: "Метод CriticalSectionTraits::Unlock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs: C++
helpviewer_keywords: Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 078ec4a1fa1af6c4660ff1171ab1b671ee9872f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="criticalsectiontraitsunlock-method"></a>Метод CriticalSectionTraits::Unlock
Специализирует шаблон CriticalSection так, чтобы она поддерживала снимать владения объектом указанного критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cs`  
 Указатель на объект критической секции.  
  
## <a name="remarks"></a>Примечания  
 *Тип* модификатор определяется как `typedef CRITICAL_SECTION* Type;`.  
  
 Дополнительные сведения см. в разделе «LeaveCriticalSection функции» в разделе «Функции синхронизации» в документации Windows API.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Структура CriticalSectionTraits](../windows/criticalsectiontraits-structure.md)