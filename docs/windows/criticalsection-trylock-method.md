---
title: "Метод CriticalSection::TryLock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2bd717e3a91d2e0210adced36e33a89f3752fa8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontrylock-method"></a>Метод CriticalSection::TryLock
Попытки ввода критической секции без блокировки. При успешном вызове вызывающий поток принимает право на владение критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cs`  
 Определенный пользователем объект критической секции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если критический раздел успешно вошел или текущий поток уже владеет критической секции. Нуль, если другой поток уже является владельцем критической секции.  
  
## <a name="remarks"></a>Примечания  
 Первый **TryLock** функция влияет на текущий объект критической секции. Второй **TryLock** функция влияет на определяемый пользователем критической секции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс CriticalSection](../windows/criticalsection-class.md)