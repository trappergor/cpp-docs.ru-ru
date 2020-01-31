---
title: ArgTraits - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
- event/Microsoft::WRL::Details::ArgTraits::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraits structure
- Microsoft::WRL::Details::ArgTraits::args constant
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
ms.openlocfilehash: c13e7fec3289b66b40e44f91404a50cba7a473b1
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821718"
---
# <a name="argtraits-structure"></a>ArgTraits - структура

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename TMemberFunction>
struct ArgTraits;

template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;

template<typename TDelegateInterface, typename TArg1>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;

template<typename TDelegateInterface, typename TArg1, typename TArg2>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>Параметры

*тмемберфунктион*<br/>
Параметр TypeName для структуры константа ArgTraits, который не может совпадать ни с одной сигнатурой метода `Invoke`.

*тделегатеинтерфаце*<br/>
Интерфейс делегата.

*TArg1*<br/>
Тип первого аргумента метода `Invoke`.

*TArg2*<br/>
Тип второго аргумента метода `Invoke`.

*TArg3*<br/>
Тип третьего аргумента метода `Invoke`.

*TArg4*<br/>
Тип четвертого аргумента метода `Invoke`.

*TArg5*<br/>
Тип пятого аргумента метода `Invoke`.

*TArg6*<br/>
Тип шестого аргумента метода `Invoke`.

*TArg7*<br/>
Тип седьмого аргумента метода `Invoke`.

*TArg8*<br/>
Тип восьмого аргумента метода `Invoke`.

*TArg9*<br/>
Тип девятого аргумента метода `Invoke`.

## <a name="remarks"></a>Заметки

Структура `ArgTraits` объявляет указанный интерфейс делегата и анонимную функцию-член, которая принимает указанное число параметров.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Открытые определения типов

Name       | Описание
---------- | ----------------------
`Arg1Type` | Typedef для TArg1.
`Arg2Type` | Typedef для TArg2.
`Arg3Type` | Typedef для TArg3.
`Arg4Type` | Typedef для TArg4.
`Arg5Type` | Typedef для TArg5.
`Arg6Type` | Typedef для TArg6.
`Arg7Type` | Typedef для TArg7.
`Arg8Type` | Typedef для TArg8.
`Arg9Type` | Typedef для TArg9.

### <a name="public-constants"></a>Открытые константы

Name                     | Описание
------------------------ | ---------------------------------------------------------------------------------------
[Константа ArgTraits:: args](#args) | Сохраняет количество параметров в методе `Invoke` интерфейса делегата.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ArgTraits`

## <a name="requirements"></a>Требования

**Заголовок:** Event. h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="args"></a>Константа ArgTraits:: args

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
static const int args = -1;
```

### <a name="remarks"></a>Заметки

Сохраняет количество параметров в методе `Invoke` интерфейса делегата. Если `args` равно-1, для сигнатуры метода `Invoke` не может быть совпадения.
