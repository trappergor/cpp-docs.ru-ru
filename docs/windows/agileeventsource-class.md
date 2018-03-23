---
title: Класс AgileEventSource | Документы Microsoft
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
dev_langs:
- C++
helpviewer_keywords:
- AgileEventSource class
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d025fc2be86fb5b59107d1deee39962c3c6db04
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="agileeventsource-class"></a>Класс AgileEventSource
Представляет событие agile. Наследует от [EventSource](eventsource-class.md) и переопределяет `Add` функция-член с параметром еще один тип для указания параметров для способы вызова agile событий.
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```  
  
#### <a name="parameters"></a>Параметры  
 `TDelegateInterface`  
 Интерфейс делегат, представляющий обработчик событий.

 `TEventSourceOptions` [InvokeModeOptions](invokemodeoptions-structure.md) структура имеет значение, поле которого invokeMode `InvokeMode::StopOnFirstError` или `InvokeMode::FireAll`.

## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[AgileEventSource::Add Method](#add)|Добавляет обработчик событий agile, представленный указанным интерфейсом делегата набору обработчиков событий для текущего объекта AgileEventSource.|  

## <a name="add"></a> Метод AgileEventSource::Add

Добавляет обработчик событий, представленный указанным интерфейсом делегата, к набору обработчиков событий для текущего объекта EventSource.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);
```

### <a name="parameters"></a>Параметры

*delegateInterface*

Интерфейс для объекта делегата, который представляет обработчик событий.

*токен* после завершения операции дескриптор, представляющий событие. Используйте этот маркер в качестве параметра в метод Remove() для удаления обработчика событий.

### <a name="return-value"></a>Возвращаемое значение
Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `EventSource`  
 `AgileEventSource`
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)