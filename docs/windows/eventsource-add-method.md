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
ms.openlocfilehash: 90750f965768d5ecda40e074f9a136407613d2d2
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570393"
---
# <a name="eventsourceadd-method"></a>Метод EventSource::Add
Добавляет обработчик событий, представленный указанным интерфейсом делегата к набору обработчиков событий для текущего **EventSource** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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