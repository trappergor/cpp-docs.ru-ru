---
title: Метод EventSource::Remove | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Remove
dev_langs:
- C++
helpviewer_keywords:
- Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36a057bbad39e61576828c5a02f6863248b235cf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641409"
---
# <a name="eventsourceremove-method"></a>Метод EventSource::Remove
Удаляет обработчик событий, представленного маркером регистрации указанное событие из набора обработчиков событий, связанных с текущим **EventSource** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *Маркер*  
 Дескриптор, который представляет обработчик событий. Этот токен был возвращен при регистрации обработчика событий с [Add()](../windows/eventsource-add-method.md) метод.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о `EventRegistrationToken` структуры, см. в разделе **структуры Windows::Foundation:: eventregistrationtoken** подразделы **среды выполнения Windows** справочной документации.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс EventSource](../windows/eventsource-class.md)