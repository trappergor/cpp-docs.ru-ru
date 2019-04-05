---
title: Класс AgileEventSource
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- AgileEventSource class
ms.openlocfilehash: 095c61dcef208028bf1c0f4b3443ba10110da8ed
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025870"
---
# <a name="agileeventsource-class"></a>Класс AgileEventSource

Представляет событие, произошедшее в компоненте agile, который является компонентом, который может осуществляться из любого потока. Наследует от [EventSource](eventsource-class.md) и переопределяет `Add` функция-член с параметром дополнительный тип для указания параметров для способ вызова agile события.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    typename TDelegateInterface,
    typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>
>
class AgileEventSource :
    public Microsoft::WRL::EventSource<
        TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>Параметры

*TDelegateInterface*<br/>
Интерфейс делегат, представляющий обработчик событий.

*TEventSourceOptions*<br/>
[InvokeModeOptions](invokemodeoptions-structure.md) структура, поля которого invokeMode задается `InvokeMode::StopOnFirstError` или `InvokeMode::FireAll`.

## <a name="remarks"></a>Примечания

Подавляющее большинство компонентов в среде выполнения Windows — agile компоненты. Дополнительные сведения см. в разделе [работа с потоками и маршалинг (C + +/ CX)](../../cppcx/threading-and-marshaling-c-cx.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EventSource`

`AgileEventSource`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Метод AgileEventSource::Add](#add)|Добавляет обработчик событий agile, представленный указанным интерфейсом делегата к набору обработчиков событий для текущего **AgileEventSource** объекта.|

## <a name="add"></a> Метод AgileEventSource::Add

Добавляет обработчик событий, представленный указанным интерфейсом делегата к набору обработчиков событий для текущего [EventSource](eventsource-class.md) объекта.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Параметры

*delegateInterface*<br/>
Интерфейс для объекта делегата, который представляет обработчик событий.

*token*<br/>
После завершения операции представляет дескриптор события. Использовать этот маркер в качестве параметра `Remove()` метод для удаления обработчика событий.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)