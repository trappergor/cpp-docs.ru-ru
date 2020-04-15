---
title: HandleT - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Get
- corewrappers/Microsoft::WRL::Wrappers::HandleT::handle_
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
- corewrappers/Microsoft::WRL::Wrappers::HandleT::~HandleT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleT class
- Microsoft::WRL::Wrappers::HandleT::Attach method
- Microsoft::WRL::Wrappers::HandleT::Close method
- Microsoft::WRL::Wrappers::HandleT::Detach method
- Microsoft::WRL::Wrappers::HandleT::Get method
- Microsoft::WRL::Wrappers::HandleT::handle_ data member
- Microsoft::WRL::Wrappers::HandleT::HandleT, constructor
- Microsoft::WRL::Wrappers::HandleT::InternalClose method
- Microsoft::WRL::Wrappers::HandleT::IsValid method
- Microsoft::WRL::Wrappers::HandleT::operator= operator
- Microsoft::WRL::Wrappers::HandleT::~HandleT, destructor
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
ms.openlocfilehash: bde7d7f1bd6730d96cb0f7a0d191a32eb8ed3e8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371455"
---
# <a name="handlet-class"></a>HandleT - класс

Представляет дескриптор объекта.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>Параметры

*HandleTraits*<br/>
Пример структуры [HandleTraits,](handletraits-structure.md) определяющий общие характеристики рукоятки.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя     | Описание
-------- | -----------------------------
`Traits` | Синоним для `HandleTraits`.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                | Описание
----------------------------------- | --------------------------------------------------
[Ручка::Ручка](#handlet)        | Инициализирует новый экземпляр класса `HandleT`.
[HandleT:::-HandleT](#tilde-handlet) | Деприиратизирует экземпляр `HandleT` класса.

### <a name="public-methods"></a>Открытые методы

Имя                         | Описание
---------------------------- | ----------------------------------------------------------------------
[HandleT::Attach](#attach)   | Связывает указанную ручку `HandleT` с текущим объектом.
[HandleT::Закрыть](#close)     | Закрывает текущий объект `HandleT`.
[РучкаT::Detach](#detach)   | Отсаживая `HandleT` текущий объект от основной ручки.
[HandleT::Get](#get)         | Получает значение основной ручки.
[Ручка::Действительно](#isvalid) | Указывает, представляет `HandleT` ли текущий объект ручку.

### <a name="protected-methods"></a>Защищенные методы

Имя                                     | Описание
---------------------------------------- | ------------------------------------
[HandleT::Internalclose](#internalclose) | Закрывает текущий объект `HandleT`.

### <a name="public-operators"></a>Открытые операторы

Имя                                   | Описание
-------------------------------------- | ----------------------------------------------------------------------------------
[Ручка:оператор](#operator-assign) | Перемещает значение указанного `HandleT` объекта к `HandleT` текущему объекту.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                        | Описание
--------------------------- | ----------------------------------------------------------------
[Ручка::handle_](#handle) | Содержит ручку, представленную `HandleT` объектом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HandleT`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Wrappers

## <a name="handlethandlet"></a><a name="tilde-handlet"></a>HandleT:::-HandleT

Деприиратизирует экземпляр `HandleT` класса.

```cpp
~HandleT();
```

## <a name="handletattach"></a><a name="attach"></a>HandleT::Attach

Связывает указанную ручку `HandleT` с текущим объектом.

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Дескриптор.

## <a name="handletclose"></a><a name="close"></a>HandleT::Закрыть

Закрывает текущий объект `HandleT`.

```cpp
void Close();
```

### <a name="remarks"></a>Remarks

Ручка, лежащая `HandleT` в основе тока, закрыта, а `HandleT` настроена на недействительное состояние.

Если дескриптор не закрывается правильно, возникает исключение в вызывающем потоке.

## <a name="handletdetach"></a><a name="detach"></a>РучкаT::Detach

Отсаживая `HandleT` текущий объект от основной ручки.

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Основная ручка.

### <a name="remarks"></a>Remarks

Когда эта операция завершается, ток `HandleT` устанавливается в недействительное состояние.

## <a name="handletget"></a><a name="get"></a>HandleT::Get

Получает значение основной ручки.

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор.

## <a name="handlethandle_"></a><a name="handle"></a>Ручка::handle_

Содержит ручку, представленную `HandleT` объектом.

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlethandlet"></a><a name="handlet"></a>Ручка::Ручка

Инициализирует новый экземпляр класса `HandleT`.

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Дескриптор.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует `HandleT` объект, который не является допустимой ручкой для объекта. Второй конструктор создает новый `HandleT` объект из параметра *h.*

## <a name="handletinternalclose"></a><a name="internalclose"></a>HandleT::Internalclose

Закрывает текущий объект `HandleT`.

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `HandleT` ток закрылся успешно; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Параметр `InternalClose()` равен `protected`.

## <a name="handletisvalid"></a><a name="isvalid"></a>Ручка::Действительно

Указывает, представляет `HandleT` ли текущий объект ручку.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** `HandleT` если представляет собой ручку; в противном случае, **ложные**.

## <a name="handletoperator"></a><a name="operator-assign"></a>Ручка:оператор

Перемещает значение указанного `HandleT` объекта к `HandleT` текущему объекту.

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Rvalue-ссылка на ручку.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `HandleT` текущий объект.

### <a name="remarks"></a>Remarks

Эта операция аннулирует объект, указанный `HandleT` по параметру *h*.
