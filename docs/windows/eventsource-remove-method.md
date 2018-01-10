---
title: "Метод EventSource::Remove | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::Remove
dev_langs: C++
helpviewer_keywords: Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a11bce6d70c70bba2a4e75753c55d83bec32329f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="eventsourceremove-method"></a>Метод EventSource::Remove
Удаляет обработчик событий, представленного маркером регистрации указанное событие из набора обработчиков событий, связанных с текущим объектом EventSource.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `token`  
 Дескриптор, представляющий обработчик событий. Этот маркер был возвращен во время регистрации обработчика событий [Add()](../windows/eventsource-add-method.md) метод.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о структуре EventRegistrationToken см. в разделе Windows::Foundation:: eventregistrationtoken структуры в справочной документации среды выполнения Windows.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс EventSource](../windows/eventsource-class.md)