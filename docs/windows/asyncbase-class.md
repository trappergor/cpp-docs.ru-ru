---
title: Класс AsyncBase | Документация Майкрософт
ms.custom: ''
ms.date: 10/08/2018
ms.technology:
- cpp-windows
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
- async/Microsoft::WRL::AsyncBase::Start
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
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
- Microsoft::WRL::AsyncBase::Start method
- Microsoft::WRL::AsyncBase::TryTransitionToCompleted method
- Microsoft::WRL::AsyncBase::TryTransitionToError method
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9647e18af021caf67dea5d946c9e5bf00fb50807
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162936"
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
Обработчик событий, вызываемый при завершении асинхронной операции.

*TProgress*<br/>
Обработчик событий, вызываемый при асинхронной операции отображается ход выполнения текущей операции.

*Тип resultType*<br/>
Один из [AsyncResultType](../windows/asyncresulttype-enumeration.md) значений перечисления. По умолчанию `SingleResult`.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                               | Описание
---------------------------------- | -------------------------------------------------
[AsyncBase::AsyncBase](#asyncbase) | Инициализирует экземпляр класса `AsyncBase`.

### <a name="public-methods"></a>Открытые методы

Имя                                         | Описание
-------------------------------------------- | -------------------------------------------------------------------------------------
[AsyncBase::Cancel](#cancel)                 | Отменяет асинхронную операцию.
[AsyncBase::Close](#close)                   | Закрывает асинхронной операции.
[AsyncBase::FireCompletion](#firecompletion) | Вызывает обработчик события завершения или сбрасывает делегат внутренней хода выполнения.
[AsyncBase::FireProgress](#fireprogress)     | Вызывает текущий обработчик событий процесса выполнения.
[AsyncBase::get_ErrorCode](#get-errorcode)   | Получает код ошибки для текущей асинхронной операции.
[AsyncBase::get_Id](#get-id)                 | Извлекает дескриптор асинхронной операции.
[AsyncBase::get_Status](#get-status)         | Получает значение, указывающее состояние асинхронной операции.
[AsyncBase::GetOnComplete](#getoncomplete)   | Копирует адрес текущего обработчика событий завершения в указанной переменной.
[AsyncBase::GetOnProgress](#getonprogress)   | Копирует адрес текущего обработчика событий процесса выполнения в указанную переменную.
[AsyncBase::put_Id](#put-id)                 | Задает дескриптор асинхронной операции.
[AsyncBase::PutOnComplete](#putoncomplete)   | Задает адрес обработчик события завершения для указанного значения.
[AsyncBase::PutOnProgress](#putonprogress)   | Задает адрес обработчика событий процесса выполнения указанное значение.
[AsyncBase::Start](#start)                   | Начинает асинхронную операцию.

### <a name="protected-methods"></a>Защищенные методы

Имя                                                                         | Описание
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[AsyncBase::CheckValidStateForDelegateCall](#checkvalidstatefordelegatecall) | Проверяет, является ли делегат свойства можно изменить в текущем состоянии асинхронной.
[AsyncBase::CheckValidStateForResultsCall](#checkvalidstateforresultscall)   | Проверяет, является ли результаты асинхронной операции можно собирать в текущем состоянии асинхронной.
[AsyncBase::ContinueAsyncOperation](#continueasyncoperation)                 | Определяет, должны продолжать обработку асинхронной операции или следует остановить.
[AsyncBase::CurrentStatus](#currentstatus)                                   | Извлекает состояние текущей асинхронной операции.
[AsyncBase::ErrorCode](#errorcode)                                           | Получает код ошибки для текущей асинхронной операции.
[AsyncBase::OnCancel](#oncancel)                                             | При переопределении в производном классе отменяет асинхронную операцию.
[AsyncBase::OnClose](#onclose)                                               | При переопределении в производном классе, закрывает асинхронной операции.
[AsyncBase::OnStart](#onstart)                                               | При переопределении в производном классе запускает асинхронную операцию.
[AsyncBase::TryTransitionToCompleted](#trytransitiontocompleted)             | Указывает, завершена ли текущей асинхронной операции.
[AsyncBase::TryTransitionToError](#trytransitiontoerror)                     | Указывает, является ли указанный код ошибки можно изменить внутреннее состояние ошибки.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL

## <a name="asyncbase"></a>AsyncBase::AsyncBase

Инициализирует экземпляр класса `AsyncBase`.

```cpp
AsyncBase();
```

## <a name="cancel"></a>AsyncBase::Cancel

Отменяет асинхронную операцию.

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>Возвращаемое значение

По умолчанию всегда возвращает значение S_OK.

### <a name="remarks"></a>Примечания

`Cancel()` — Это реализация по умолчанию `IAsyncInfo::Cancel`, а не фактические работает. Действительно отменить асинхронную операцию, переопределить `OnCancel()` чисто виртуального метода.

## <a name="checkvalidstatefordelegatecall"></a>AsyncBase::CheckValidStateForDelegateCall

Проверяет, является ли делегат свойства можно изменить в текущем состоянии асинхронной.

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если делегат свойства можно изменить; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="checkvalidstateforresultscall"></a>AsyncBase::CheckValidStateForResultsCall

Проверяет, является ли результаты асинхронной операции можно собирать в текущем состоянии асинхронной.

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если результаты могут быть собраны; в противном случае E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.

## <a name="close"></a>AsyncBase::Close

Закрывает асинхронной операции.

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция закрывает или уже закрыт; в противном случае E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Примечания

`Close()` — Это реализация по умолчанию `IAsyncInfo::Close`, а не фактические работает. Чтобы действительно закрыть асинхронную операцию, переопределите `OnClose()` чисто виртуального метода.

## <a name="continueasyncoperation"></a>AsyncBase::ContinueAsyncOperation

Определяет, должны продолжать обработку асинхронной операции или следует остановить.

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если текущее состояние асинхронной операции *работы*, который означает, что операция должна продолжаться. В противном случае **false**, который означает, что операция следует остановить.

## <a name="currentstatus"></a>AsyncBase::CurrentStatus

Извлекает состояние текущей асинхронной операции.

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Параметры

*status*<br/>
Расположение, в котором эта операция сохраняет текущее состояние.

### <a name="remarks"></a>Примечания

Данная операция является потокобезопасной.

## <a name="errorcode"></a>AsyncBase::ErrorCode

Получает код ошибки для текущей асинхронной операции.

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>Параметры

*Ошибка*<br/>
Расположение, в котором эта операция сохраняет текущий код ошибки.

### <a name="remarks"></a>Примечания

Данная операция является потокобезопасной.

## <a name="firecompletion"></a>AsyncBase::FireCompletion

Вызывает обработчик события завершения или сбрасывает делегат внутренней хода выполнения.

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>Примечания

Первая версия `FireCompletion()` сбрасывает переменной делегата внутренней хода выполнения. Вторая версия вызывает обработчик события завершения, если асинхронная операция завершена.

## <a name="fireprogress"></a>AsyncBase::FireProgress

Вызывает текущий обработчик событий процесса выполнения.

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>Параметры

*arg*<br/>
Метод обработчика событий для запуска.

### <a name="remarks"></a>Примечания

`ProgressTraits` является производным от [argtraitshelper-структура](../windows/argtraitshelper-structure.md).

## <a name="get-errorcode"></a>AsyncBase::get_ErrorCode

Получает код ошибки для текущей асинхронной операции.

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>Параметры

*код ошибки*<br/>
Расположение, где хранится текущий код ошибки.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL, если текущей асинхронной операции закрытия.

## <a name="get-id"></a>AsyncBase::get_Id

Извлекает дескриптор асинхронной операции.

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>Параметры

*id*<br/>
Расположение, где будет храниться дескриптор.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Примечания

Этот метод реализует `IAsyncInfo::get_Id`.

## <a name="get-status"></a>AsyncBase::get_Status

Получает значение, указывающее состояние асинхронной операции.

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>Параметры

*status*<br/>
Расположение, где будет храниться состояние. Дополнительные сведения см. в разделе `Windows::Foundation::AsyncStatus` перечисления.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Примечания

Этот метод реализует `IAsyncInfo::get_Status`.

## <a name="getoncomplete"></a>AsyncBase::GetOnComplete

Копирует адрес текущего обработчика событий завершения в указанной переменной.

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>Параметры

*completeHandler*<br/>
Расположение, где хранится адрес текущего обработчика событий завершения.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="getonprogress"></a>AsyncBase::GetOnProgress

Копирует адрес текущего обработчика событий процесса выполнения в указанную переменную.

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>Параметры

*progressHandler*<br/>
Расположение, в котором сохраняется адрес текущего обработчика событий процесса выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="oncancel"></a>AsyncBase::OnCancel

При переопределении в производном классе отменяет асинхронную операцию.

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="onclose"></a>AsyncBase::OnClose

При переопределении в производном классе, закрывает асинхронной операции.

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="onstart"></a>AsyncBase::OnStart

При переопределении в производном классе запускает асинхронную операцию.

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="put-id"></a>AsyncBase::put_Id

Задает дескриптор асинхронной операции.

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>Параметры

*id*<br/>
Ненулевое значение дескриптора.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение E_INVALIDARG или E_ILLEGAL_METHOD_CALL.

## <a name="putoncomplete"></a>AsyncBase::PutOnComplete

Задает адрес обработчик события завершения для указанного значения.

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>Параметры

*completeHandler*<br/>
Адрес, к которому устанавливается обработчик события завершения.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="putonprogress"></a>AsyncBase::PutOnProgress

Задает адрес обработчика событий процесса выполнения указанное значение.

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>Параметры

*progressHandler*<br/>
Адрес, задаваемое для обработчика событий процесса выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.

## <a name="start"></a>AsyncBase::Start

Начинает асинхронную операцию.

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция запускается или уже запущен; в противном случае E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Примечания

`Start()` — Это реализация по умолчанию `IAsyncInfo::Start`, а не фактические работает. Чтобы фактически запускает асинхронную операцию, переопределите `OnStart()` чисто виртуального метода.

## <a name="trytransitiontocompleted"></a>AsyncBase::TryTransitionToCompleted

Указывает, завершена ли текущей асинхронной операции.

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если асинхронная операция была завершена; в противном случае **false**.

## <a name="trytransitiontoerror"></a>AsyncBase::TryTransitionToError

Указывает, является ли указанный код ошибки можно изменить внутреннее состояние ошибки.

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>Параметры

*Ошибка*<br/>
Ошибка HRESULT.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** если внутреннее состояние ошибки было изменено; в противном случае — значение **false**.

### <a name="remarks"></a>Примечания

Эта операция изменяет состояние ошибки только в том случае, если состояние ошибки уже имеет значение S_OK. Эта операция не оказывает влияния Если состояние ошибки не ошибка, отменено, завершено или закрыт.
