---
title: Метод DeferrableEventArgs::InvokeAllFinished | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1aaaf8c6849b30e26463810ff353234319960048
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883372"
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