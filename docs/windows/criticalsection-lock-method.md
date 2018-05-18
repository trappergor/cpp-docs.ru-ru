---
title: Метод CriticalSection::Lock | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c873494a702802b8ead3dab9cac28557664f618
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="criticalsectionlock-method"></a>Метод CriticalSection::Lock
Ожиданий владения объектом указанного критической секции. Эта функция возвращает при предоставлении владельцем вызывающего потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cs`  
 Определенный пользователем объект критической секции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект блокировки, который можно использовать, чтобы разблокировать текущую критическую секцию.  
  
## <a name="remarks"></a>Примечания  
 Первый **блокировки** функция влияет на текущий объект критической секции. Второй **блокировки** функция влияет на определяемый пользователем критической секции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс CriticalSection](../windows/criticalsection-class.md)