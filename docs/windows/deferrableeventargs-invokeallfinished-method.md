---
title: "Метод DeferrableEventArgs::InvokeAllFinished | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ca021d66c615bfec84b8f08df8474eeb20709e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="deferrableeventargsinvokeallfinished-method"></a>Метод DeferrableEventArgs::InvokeAllFinished
Вызывается, чтобы указать, что вся обработка для отложенного события завершена.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void InvokeAllFinished()  
```  
  
## <a name="remarks"></a>Примечания  
 Этот метод следует вызывать после источник события вызовет [InvokeAll](../windows/eventsource-invokeall-method.md). Вызов этого метода предотвращает ввод последующих задержек и вызывает принудительное выполнение обработчика завершения, если задержки отсутствовали.  
  
 Пример кода см. в разделе [класс DeferrableEventArgs](../windows/deferrableeventargs-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс DeferrableEventArgs](../windows/deferrableeventargs-class.md)   
 [Метод EventSource::InvokeAll](../windows/eventsource-invokeall-method.md)