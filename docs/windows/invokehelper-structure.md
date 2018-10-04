---
title: Invokehelper-структура | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 46cd067e41fcc9ac0d8d3dd9fe50c9edd23532c3
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789115"
---
# <a name="invokehelper-structure"></a>InvokeHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename TDelegateInterface, typename TCallback, unsigned int argCount>
struct InvokeHelper;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 0> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 1> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 2> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 3> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 4> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 5> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 6> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 7> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 8> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 9> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;
```

### <a name="parameters"></a>Параметры

*TDelegateInterface*<br/>
*TCallback*  
Тип функции обработчика событий.

*argCount*<br/>
Число аргументов в `InvokeHelper` специализации.

## <a name="remarks"></a>Примечания

Предоставляет реализацию `Invoke()` метод на основе заданного числа и типа аргументов.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя     | Описание
-------- | -----------------------------------------------------------------------------
`Traits` | Синоним для класса, который определяет тип каждого аргумента обработчика событий.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                        | Описание
------------------------------------------- | -------------------------------------------------------
[InvokeHelper::InvokeHelper](#invokehelper) | Инициализирует новый экземпляр класса `InvokeHelper`.

### <a name="public-methods"></a>Открытые методы

Имя                            | Описание
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper::Invoke](#invoke) | Вызывает обработчик событий, сигнатура которого содержит указанное число аргументов.

### <a name="public-data-members"></a>Открытые члены данных

Имя                                 | Описание
------------------------------------ | ----------------------------------------------------------
[InvokeHelper::callback_](#callback) | Представляет обработчик событий для вызова при возникновении события.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InvokeHelper`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="callback"></a>InvokeHelper::callback_

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>Примечания

Представляет обработчик событий для вызова при возникновении события.

`TCallback` Параметр шаблона тип обработчика событий.

## <a name="invoke"></a>InvokeHelper::Invoke

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
STDMETHOD(
   Invoke
)();
STDMETHOD(
   Invoke
)(typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
```

### <a name="parameters"></a>Параметры

*arg1*<br/>
Аргумент 1.

*Arg2*<br/>
Аргумент 2.

*arg3*<br/>
Аргумент 3.

*arg4*<br/>
Аргумент 4.

*arg5*<br/>
Аргумент 5.

*arg6*<br/>
Аргумент 6.

*arg7*<br/>
Аргумент 7.

*arg8*<br/>
Аргумент 8.

*arg9*<br/>
Аргумент 9.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, описывающее ошибку.

### <a name="remarks"></a>Примечания

Вызывает обработчик событий, сигнатура которого содержит указанное число аргументов.

## <a name="invokehelper"></a>InvokeHelper::InvokeHelper

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Параметры

*обратный вызов*<br/>
Обработчик событий.

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `InvokeHelper`.

`TCallback` Параметр шаблона тип обработчика событий.
