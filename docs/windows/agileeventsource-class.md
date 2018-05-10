---
title: Класс AgileEventSource | Документы Microsoft
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58eb96e3a0268d3ba70b60d9c315e935e19485f3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="agileeventsource-class"></a>Класс AgileEventSource

Представляет событие, произошедшее в гибкой компонент, который является компонентом, который может осуществляться из любого потока. Наследует от [EventSource](eventsource-class.md) и переопределяет `Add` функция-член с параметром еще один тип для указания параметров для способы вызова agile событий.

## <a name="syntax"></a>Синтаксис

```
template<typename TDelegateInterface, typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>>
class AgileEventSource
    : public Microsoft::WRL::EventSource<TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>Параметры  
 `TDelegateInterface`  

 Интерфейс делегат, представляющий обработчик событий.

 `TEventSourceOptions`  
 [InvokeModeOptions](invokemodeoptions-structure.md) структура имеет значение, поле которого invokeMode `InvokeMode::StopOnFirstError` или `InvokeMode::FireAll`.

## <a name="remarks"></a>Примечания

Большинство компонентов в среде выполнения Windows являются гибкими компонентами. Дополнительные сведения см. в разделе [работа с потоками и маршалинг (C + +/ CX)](../cppcx/threading-and-marshaling-c-cx.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

 `EventSource` `AgileEventSource`

## <a name="requirements"></a>Требования

 **Заголовок:** event.h

 **Пространство имен:** Microsoft::WRL

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод AgileEventSource::Add](#add)|Добавляет обработчик событий agile, представленный указанным интерфейсом делегата набору обработчиков событий для текущего объекта AgileEventSource.|

## <a name="add"></a> Метод AgileEventSource::Add

Добавляет обработчик событий, представленный указанным интерфейсом делегата набору обработчиков событий для текущего [EventSource](eventsource-class.md) объекта.

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


## <a name="see-also"></a>См. также

 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)
