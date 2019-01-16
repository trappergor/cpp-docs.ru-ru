---
title: Класс DeferrableEventArgs
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
ms.openlocfilehash: 509686556bd06a6ec9d059593be46d0fc6a3876d
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336656"
---
# <a name="deferrableeventargs-class"></a>Класс DeferrableEventArgs

Класс шаблона, используемый для типов аргументов событий для задержек.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>Параметры

*TEventArgsInterface*<br/>
Тип интерфейса, который объявляет аргументы для отложенного события.

*TEventArgsClass*<br/>
Класс, реализующий *TEventArgsInterface*.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

Имя                                                         | Описание
------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------
[DeferrableEventArgs::GetDeferral](#getdeferral)             | Получает ссылку на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, который представляет отложенное событие.
[DeferrableEventArgs::InvokeAllFinished](#invokeallfinished) | Вызывается, чтобы указать, что вся обработка для отложенного события завершена.

## <a name="remarks"></a>Примечания

Экземпляры этого класса передаются в обработчики событий для отложенных событий. Параметры шаблона представляют интерфейс, определяющий подробные сведения об аргументах событий для конкретного типа отложенного события, а также класс, реализующий этот интерфейс.

Класс отображается как первый аргумент обработчика событий для отложенного события. Можно вызвать [задержка](#getdeferral) метод для получения [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, из которого можно получить все сведения об отложенном событии. После завершения обработки событий необходимо вызвать завершение в объекте «Задержка». Затем следует вызвать [InvokeAllFinished](#invokeallfinished) в конце метода обработчика событий, который гарантирует, что завершение всех отложенных событий передается надлежащим образом.

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="getdeferral"></a>DeferrableEventArgs::GetDeferral

Получает ссылку на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объект, который представляет отложенное событие.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>Параметры

*результат*<br/>
Указатель, который будет ссылаться на [отсрочки](http://go.microsoft.com/fwlink/p/?linkid=526520) объекта после завершения вызова.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="invokeallfinished"></a>DeferrableEventArgs::InvokeAllFinished

Вызывается, чтобы указать, что вся обработка для отложенного события завершена.

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>Примечания

Этот метод следует вызывать после источник события вызовет [InvokeAll](eventsource-class.md#invokeall). Вызов этого метода предотвращает ввод последующих задержек и вызывает принудительное выполнение обработчика завершения, если задержки отсутствовали.
