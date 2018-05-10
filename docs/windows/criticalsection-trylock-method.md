---
title: Метод CriticalSection::TryLock | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b4ee99d82212d0d6cdd610b4565bd9292a0265dc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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