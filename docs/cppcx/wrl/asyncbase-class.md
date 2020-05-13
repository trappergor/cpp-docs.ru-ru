---
title: AsyncBase - класс
ms.date: 10/08/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
- async/Microsoft::WRL::AsyncBase::AsyncBase
- async/Microsoft::WRL::AsyncBase::Cancel
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
- async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall
- async/Microsoft::WRL::AsyncBase::Close
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
- async/Microsoft::WRL::AsyncBase::CurrentStatus
- async/Microsoft::WRL::AsyncBase::ErrorCode
- async/Microsoft::WRL::AsyncBase::FireCompletion
- async/Microsoft::WRL::AsyncBase::FireProgress
- async/Microsoft::WRL::AsyncBase::get_ErrorCode
- async/Microsoft::WRL::AsyncBase::get_Id
- async/Microsoft::WRL::AsyncBase::get_Status
- async/Microsoft::WRL::AsyncBase::GetOnComplete
- async/Microsoft::WRL::AsyncBase::GetOnProgress
- async/Microsoft::WRL::AsyncBase::OnCancel
- async/Microsoft::WRL::AsyncBase::OnClose
- async/Microsoft::WRL::AsyncBase::OnStart
- async/Microsoft::WRL::AsyncBase::put_Id
- async/Microsoft::WRL::AsyncBase::PutOnComplete
- async/Microsoft::WRL::AsyncBase::PutOnProgress
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
helpviewer_keywords:
- Microsoft::WRL::AsyncBase class
- Microsoft::WRL::AsyncBase::AsyncBase, constructor
- Microsoft::WRL::AsyncBase::Cancel method
- Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall method
- Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall method
- Microsoft::WRL::AsyncBase::Close method
- Microsoft::WRL::AsyncBase::ContinueAsyncOperation method
- Microsoft::WRL::AsyncBase::CurrentStatus method
- Microsoft::WRL::AsyncBase::ErrorCode method
- Microsoft::WRL::AsyncBase::FireCompletion method
- Microsoft::WRL::AsyncBase::FireProgress method
- Microsoft::WRL::AsyncBase::get_ErrorCode method
- Microsoft::WRL::AsyncBase::get_Id method
- Microsoft::WRL::AsyncBase::get_Status method
- Microsoft::WRL::AsyncBase::GetOnComplete method
- Microsoft::WRL::AsyncBase::GetOnProgress method
- Microsoft::WRL::AsyncBase::OnCancel method
- Microsoft::WRL::AsyncBase::OnClose method
- Microsoft::WRL::AsyncBase::OnStart method
- Microsoft::WRL::AsyncBase::put_Id method
- Microsoft::WRL::AsyncBase::PutOnComplete method
- Microsoft::WRL::AsyncBase::PutOnProgress method
- Microsoft::WRL::AsyncBase::TryTransitionToCompleted method
- Microsoft::WRL::AsyncBase::TryTransitionToError method
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
ms.openlocfilehash: 0254aa4dc243eeffa43850c437a833a6530c01e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371861"
---
# <a name="asyncbase-class"></a>AsyncBase - класс

Реализует асинхронный конечный автомат среды выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename TComplete,
    typename TProgress = Details::Nil,
    AsyncResultType resultType = SingleResult
>
class AsyncBase : public AsyncBase<TComplete, Details::Nil, resultType>;

template <typename TComplete, AsyncResultType resultType>
class AsyncBase<TComplete, Details::Nil, resultType> :
    public Microsoft::WRL::Implements<IAsyncInfo>;
```

### <a name="parameters"></a>Параметры

*TComplete*<br/>
Обработчик событий, который вызывается при завершении асинхронной операции.

*TProgress*<br/>
Обработчик событий, который вызывается при запуске асинхронной операции, сообщает о текущем ходе операции.

*resultType*<br/>
Одно из значений перечисления [AsyncResultType.](asyncresulttype-enumeration.md) По умолчанию — `SingleResult`.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                               | Описание
---------------------------------- | -------------------------------------------------
[AsyncBase:AsyncBase](#asyncbase) | Инициализирует экземпляр класса `AsyncBase`.

### <a name="public-methods"></a>Открытые методы

Имя                                         | Описание
-------------------------------------------- | -------------------------------------------------------------------------------------
[AsyncBase::Отмена](#cancel)                 | Отменяет асинхронную операцию.
[AsyncBase::Закрыть](#close)                   | Закрывает асинхронную операцию.
[AsyncBase::FireCompletion](#firecompletion) | Вызывает обработку события завершения или сбрасывает внутренний делегат прогресса.
[AsyncBase::FireProgress](#fireprogress)     | Вызывает текущий обработчик событий процесса выполнения.
[AsyncBase::get_ErrorCode](#get-errorcode)   | Извлекает код ошибки для текущей асинхронной операции.
[AsyncBase::get_Id](#get-id)                 | Извлекает ручку асинхронной операции.
[AsyncBase::get_Status](#get-status)         | Извлекает значение, указывававое состояние асинхронной операции.
[AsyncBase:Getoncomplete](#getoncomplete)   | Копирует адрес текущего обработчика событий завершения в указанную переменную.
[АsyncBase:Гетонпрогресс](#getonprogress)   | Копирует адрес текущего обработчика событий процесса выполнения в указанную переменную.
[AsyncBase::put-Id](#put-id)                 | Устанавливает ручку асинхронной операции.
[AsyncBase::Putoncomplete](#putoncomplete)   | Устанавливает адрес обработчика события завершения к указанному значению.
[AsyncBase::PutonProgress](#putonprogress)   | Устанавливает адрес обработчика события прогресса в указанное значение.

### <a name="protected-methods"></a>Защищенные методы

Имя                                                                         | Описание
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[Asyncbase::CheckvalidstateForDelegateCall](#checkvalidstatefordelegatecall) | Тестирует, можно ли модифицировать свойства делегата в текущем асинхронном состоянии.
[AsyncBase::CheckvalidstateForResultsCall](#checkvalidstateforresultscall)   | Тестирует, можно ли собирать результаты асинхронной операции в текущем асинхронном состоянии.
[AsyncBase::ПродолжениеАсиноперация](#continueasyncoperation)                 | Определяет, должна ли асинхронная операция продолжать обработку или прекратить.
[AsyncBase::Текущийстатус](#currentstatus)                                   | Извлекает состояние текущей асинхронной операции.
[AsyncBase::ОшибкаКод](#errorcode)                                           | Извлекает код ошибки для текущей асинхронной операции.
[AsyncBase::Отмена](#oncancel)                                             | При перезаходе в производном классе отмените асинхронную операцию.
[AsyncBase::Onclose](#onclose)                                               | При перечерке в производном классе замыкает асинхронную операцию.
[AsyncBase::OnStart](#onstart)                                               | При переопределении в производном классе запускает асинхронную операцию.
[AsyncBase::Начало](#start)                                                   | Начинается асинхронная операция.
[Аsyncbase:TryTransitionToЗавершена](#trytransitiontocompleted)             | Указывает, завершена ли текущая асинхронная операция.
[Asyncbase:TryTransitionToError](#trytransitiontoerror)                     | Указывает, может ли указанный код ошибки изменять состояние внутренней ошибки.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="asyncbaseasyncbase"></a><a name="asyncbase"></a>AsyncBase:AsyncBase

Инициализирует экземпляр класса `AsyncBase`.

```cpp
AsyncBase();
```

## <a name="asyncbasecancel"></a><a name="cancel"></a>AsyncBase::Отмена

Отменяет асинхронную операцию.

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>Возвращаемое значение

По умолчанию всегда возвращаетS_OK.

### <a name="remarks"></a>Remarks

`Cancel()`является реализацией `IAsyncInfo::Cancel`по умолчанию, и не делает никакой фактической работы. Чтобы на самом деле отменить асинхронную операцию, переопределить чистый виртуальный `OnCancel()` метод.

## <a name="asyncbasecheckvalidstatefordelegatecall"></a><a name="checkvalidstatefordelegatecall"></a>Asyncbase::CheckvalidstateForDelegateCall

Тестирует, можно ли модифицировать свойства делегата в текущем асинхронном состоянии.

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>Возвращаемое значение

S_OK, можно ли изменить свойства делегатов; в противном случае, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasecheckvalidstateforresultscall"></a><a name="checkvalidstateforresultscall"></a>AsyncBase::CheckvalidstateForResultsCall

Тестирует, можно ли собирать результаты асинхронной операции в текущем асинхронном состоянии.

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>Возвращаемое значение

S_OK, если результаты могут быть собраны; в противном случае, E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseclose"></a><a name="close"></a>AsyncBase::Закрыть

Закрывает асинхронную операцию.

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>Возвращаемое значение

S_OK, если операция закрыта или уже закрыта; в противном случае, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Remarks

`Close()`является реализацией `IAsyncInfo::Close`по умолчанию, и не делает никакой фактической работы. Чтобы на самом деле закрыть асинхронную операцию, переопределить чистый виртуальный `OnClose()` метод.

## <a name="asyncbasecontinueasyncoperation"></a><a name="continueasyncoperation"></a>AsyncBase::ПродолжениеАсиноперация

Определяет, должна ли асинхронная операция продолжать обработку или прекратить.

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если *текущее*состояние асинхронной операции запущено, что означает, что операция должна продолжаться. В противном случае, **ложные**, что означает, что операция должна прекратиться.

## <a name="asyncbasecurrentstatus"></a><a name="currentstatus"></a>AsyncBase::Текущийстатус

Извлекает состояние текущей асинхронной операции.

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Параметры

*состояние*<br/>
Расположение, в котором эта операция сохраняет текущее состояние.

### <a name="remarks"></a>Remarks

Данная операция является потокобезопасной.

## <a name="asyncbaseerrorcode"></a><a name="errorcode"></a>AsyncBase::ОшибкаКод

Извлекает код ошибки для текущей асинхронной операции.

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>Параметры

*error*<br/>
Место, где эта операция хранит текущий код ошибки.

### <a name="remarks"></a>Remarks

Данная операция является потокобезопасной.

## <a name="asyncbasefirecompletion"></a><a name="firecompletion"></a>AsyncBase::FireCompletion

Вызывает обработку события завершения или сбрасывает внутренний делегат прогресса.

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>Remarks

Первая версия `FireCompletion()` сбросов переменной делегата внутреннего прогресса. Вторая версия вызывает обработчик события завершения, если асинхронная операция завершена.

## <a name="asyncbasefireprogress"></a><a name="fireprogress"></a>AsyncBase::FireProgress

Вызывает текущий обработчик событий процесса выполнения.

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>Параметры

*Arg*<br/>
Метод обработчика событий для запуска.

### <a name="remarks"></a>Remarks

`ProgressTraits`является производным от [ArgTraitsHelper Структура](argtraitshelper-structure.md).

## <a name="asyncbaseget_errorcode"></a><a name="get-errorcode"></a>AsyncBase::get_ErrorCode

Извлекает код ошибки для текущей асинхронной операции.

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>Параметры

*errorCode*<br/>
Место, где хранится текущий код ошибки.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_ILLEGAL_METHOD_CALL если текущая асинхронная операция закрыта.

## <a name="asyncbaseget_id"></a><a name="get-id"></a>AsyncBase::get_Id

Извлекает ручку асинхронной операции.

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>Параметры

*id*<br/>
Место, где должна храниться ручка.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Remarks

Этот метод реализует `IAsyncInfo::get_Id`.

## <a name="asyncbaseget_status"></a><a name="get-status"></a>AsyncBase::get_Status

Извлекает значение, указывававое состояние асинхронной операции.

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>Параметры

*состояние*<br/>
Место, где должен храниться статус. Для получения дополнительной `Windows::Foundation::AsyncStatus` информации см.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Remarks

Этот метод реализует `IAsyncInfo::get_Status`.

## <a name="asyncbasegetoncomplete"></a><a name="getoncomplete"></a>AsyncBase:Getoncomplete

Копирует адрес текущего обработчика событий завершения в указанную переменную.

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>Параметры

*completeHandler*<br/>
Место, где хранится адрес текущего обработчика событий завершения.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasegetonprogress"></a><a name="getonprogress"></a>АsyncBase:Гетонпрогресс

Копирует адрес текущего обработчика событий процесса выполнения в указанную переменную.

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>Параметры

*прогрессобвейс*<br/>
Расположение, в котором сохраняется адрес текущего обработчика событий процесса выполнения.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseoncancel"></a><a name="oncancel"></a>AsyncBase::Отмена

При перезаходе в производном классе отмените асинхронную операцию.

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="asyncbaseonclose"></a><a name="onclose"></a>AsyncBase::Onclose

При перечерке в производном классе замыкает асинхронную операцию.

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="asyncbaseonstart"></a><a name="onstart"></a>AsyncBase::OnStart

При переопределении в производном классе запускает асинхронную операцию.

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="asyncbaseput_id"></a><a name="put-id"></a>AsyncBase::put-Id

Устанавливает ручку асинхронной операции.

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>Параметры

*id*<br/>
Ненуровая ручка.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_INVALIDARG или E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputoncomplete"></a><a name="putoncomplete"></a>AsyncBase::Putoncomplete

Устанавливает адрес обработчика события завершения к указанному значению.

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>Параметры

*completeHandler*<br/>
Адрес, по которому устанавливается обработчик события завершения.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputonprogress"></a><a name="putonprogress"></a>AsyncBase::PutonProgress

Устанавливает адрес обработчика события прогресса в указанное значение.

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>Параметры

*прогрессобвейс*<br/>
Адрес, на который настроен обработчик события выполнения.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasestart"></a><a name="start"></a>AsyncBase::Начало

Начинается асинхронная операция.

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>Возвращаемое значение

S_OK, если операция начинается или уже запущена; в противном случае, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Remarks

`Start()`является защищенным методом, который не виден внешне, потому что операции async "горячий старт" перед возвращением к вызывающему абоненту.

## <a name="asyncbasetrytransitiontocompleted"></a><a name="trytransitiontocompleted"></a>Аsyncbase:TryTransitionToЗавершена

Указывает, завершена ли текущая асинхронная операция.

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если асинхронная операция завершена; в противном случае, **ложные**.

## <a name="asyncbasetrytransitiontoerror"></a><a name="trytransitiontoerror"></a>Asyncbase:TryTransitionToError

Указывает, может ли указанный код ошибки изменять состояние внутренней ошибки.

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>Параметры

*error*<br/>
Ошибка HRESULT.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если состояние внутренней ошибки было изменено; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Эта операция изменяет состояние ошибки только в том случае, если состояние ошибки уже установлено для S_OK. Эта операция не имеет эффекта, если состояние ошибки уже ошибка, отменено, завершено или закрыто.
