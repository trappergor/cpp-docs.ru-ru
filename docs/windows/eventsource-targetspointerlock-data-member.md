---
title: Элемент данных Eventsource::targetspointerlock_ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::targetsPointerLock_
dev_langs:
- C++
helpviewer_keywords:
- targetsPointerLock_ data member
ms.assetid: 8f08409f-5262-4be7-9cf1-2ed15f19684a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 718a62d627f99eff24fd7c10e0280607a52e2be7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646891"
---
# <a name="eventsourcetargetspointerlock-data-member"></a>Элемент данных EventSource::targetsPointerLock_
Синхронизирует доступ к членам внутренние данные, даже когда обработчики событий для данного **EventSource** был добавлен, удален или вызванный.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Wrappers::SRWLock targetsPointerLock_;  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс EventSource](../windows/eventsource-class.md)