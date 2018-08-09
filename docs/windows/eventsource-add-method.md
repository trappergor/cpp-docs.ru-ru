---
title: Метод EventSource::Add | Документация Майкрософт
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
ms.openlocfilehash: 65e8576f069cce7d7aec2eae18ad577820ca93a4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644746"
---
# <a name="eventsourceadd-method"></a>Метод EventSource::Add
Добавляет обработчик событий, представленный указанным интерфейсом делегата к набору обработчиков событий для текущего **EventSource** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *delegateInterface*  
 Интерфейс для объекта делегата, который представляет обработчик событий.  
  
 *Маркер*  
 После завершения операции представляет дескриптор события. Используйте этот маркер в качестве параметра для [Remove()](../windows/eventsource-remove-method.md) метод для удаления обработчика событий.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс EventSource](../windows/eventsource-class.md)