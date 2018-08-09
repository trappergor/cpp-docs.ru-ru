---
title: Метод CriticalSection::TryLock | Документация Майкрософт
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
ms.openlocfilehash: 12d823cdefa90cad1e454996be274135d9e68fa9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647632"
---
# <a name="criticalsectiontrylock-method"></a>Метод CriticalSection::TryLock
Пытается войти в критическую секцию без блокировки. Если вызов был успешным, вызывающий поток получает права владения критический раздел.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *cs*  
 Определенный пользователем объект критической секции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если критический раздел успешно передан или текущий поток уже владеет критическим разделом. Нуль, если другой поток уже владеет критическим разделом.  
  
## <a name="remarks"></a>Примечания  
 Первый **TryLock** функции влияет на текущий объект критической секции. Второй **TryLock** функции влияет на определяемый пользователем критическую секцию.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс CriticalSection](../windows/criticalsection-class.md)