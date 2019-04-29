---
title: Класс Mutex
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Mutex class
- Microsoft::WRL::Wrappers::Mutex::Lock method
- Microsoft::WRL::Wrappers::Mutex::Mutex, constructor
- Microsoft::WRL::Wrappers::Mutex::operator= operator
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
ms.openlocfilehash: 93de43ac7e5314501d0391e2cde862ba32be0b4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379146"
---
# <a name="mutex-class"></a>Класс Mutex

Представляет объект синхронизации, который исключительно управляет общим ресурсом.

## <a name="syntax"></a>Синтаксис

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

name       | Описание
---------- | ------------------------------------------------------
`SyncLock` | Синоним для класса, поддерживающего синхронной блокировки.

### <a name="public-constructor"></a>Открытый конструктор

name                   | Описание
---------------------- | ------------------------------------------------
[Mutex::Mutex](#mutex) | Инициализирует новый экземпляр класса `Mutex`.

### <a name="public-members"></a>Открытые члены

name                 | Описание
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[Mutex::LOCK](#lock) | Только после текущего объекта, или `Mutex` объект, связанный с указанным дескриптором, выпуски, мьютексом или указанный интервал времени ожидания истечет.

### <a name="public-operator"></a>Открытый оператор

name                                 | Описание
------------------------------------ | ---------------------------------------------------------------------------
[Mutex::operator =](#operator-assign) | Назначает (перемещается) указанного `Mutex` объект с текущим `Mutex` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Mutex`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers

## <a name="lock"></a>Mutex::LOCK

Только после текущего объекта, или `Mutex` объект, связанный с указанным дескриптором, выпуски, мьютексом или указанный интервал времени ожидания истечет.

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>Параметры

*в миллисекундах*<br/>
Интервал времени ожидания в миллисекундах. Значение по умолчанию равно INFINITE, что означает неограниченное время ожидания.

*h*<br/>
Дескриптор `Mutex` объекта.

### <a name="return-value"></a>Возвращаемое значение

## <a name="mutex"></a>Mutex::Mutex

Инициализирует новый экземпляр класса `Mutex`.

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор или rvalue ссылка на дескриптор, чтобы `Mutex` объекта.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует `Mutex` объект из указанного дескриптора. Второй конструктор инициализирует `Mutex` объект из указанного дескриптора, а затем перемещает владение мьютексом текущему `Mutex` объекта.

## <a name="operator-assign"></a>Mutex::operator =

Назначает (перемещается) указанного `Mutex` объект с текущим `Mutex` объекта.

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на `Mutex` объекта.

### <a name="return-value"></a>Возвращаемое значение

Ссылку на текущий `Mutex` объекта.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе **семантику перемещения** раздел [декларатор ссылки Rvalue: & &](../../cpp/rvalue-reference-declarator-amp-amp.md).
