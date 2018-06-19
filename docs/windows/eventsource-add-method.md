---
title: Метод EventSource::Add | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Add
dev_langs:
- C++
helpviewer_keywords:
- Add method
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 92af8746b4d2b5ba2f379cc8660b5345b2c5f175
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873242"
---
# <a name="eventsourceadd-method"></a>Метод EventSource::Add
Добавляет обработчик событий, представленный указанным интерфейсом делегата, к набору обработчиков событий для текущего объекта EventSource.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `delegateInterface`  
 Интерфейс для объекта делегата, который представляет обработчик событий.  
  
 `token`  
 После завершения операции представляет дескриптор события. Используйте этот маркер в качестве параметра для [Remove()](../windows/eventsource-remove-method.md) метод для удаления обработчика событий.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс EventSource](../windows/eventsource-class.md)