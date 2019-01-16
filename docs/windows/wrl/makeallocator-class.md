---
title: MakeAllocator - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
- implements/Microsoft::WRL::Details::MakeAllocator::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
helpviewer_keywords:
- Microsoft::WRL::Details::MakeAllocator class
- Microsoft::WRL::Details::MakeAllocator::Allocate method
- Microsoft::WRL::Details::MakeAllocator::Detach method
- Microsoft::WRL::Details::MakeAllocator::MakeAllocator, constructor
- Microsoft::WRL::Details::MakeAllocator::~MakeAllocator, destructor
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
ms.openlocfilehash: 805f0c09b0490d8cec1a0be96dcb1fc99a051371
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336448"
---
# <a name="makeallocator-class"></a>MakeAllocator - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    typename T,
    bool hasWeakReferenceSupport =
          !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,
                        T)
>
class MakeAllocator;

template<typename T>
class MakeAllocator<T, false>;

template<typename T>
class MakeAllocator<T, true>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Имя типа.

*hasWeakReferenceSupport*<br/>
**значение true,** выделить память для объекта, который поддерживает слабых ссылок; **false** выделить память для объекта, который не поддерживает слабые ссылки.

## <a name="remarks"></a>Примечания

Выделяет память для активируемого класса, с или без поддержку слабых ссылок.

Переопределить `MakeAllocator` класс для реализации модели выделения памяти, определяемые пользователем.

`MakeAllocator` обычно используется для предотвращения утечек памяти в том случае, если объект вызывает исключение во время построения.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                  | Описание
----------------------------------------------------- | ----------------------------------------------------------------
[MakeAllocator::MakeAllocator](#makeallocator)        | Инициализирует новый экземпляр класса `MakeAllocator`.
[MakeAllocator:: ~ MakeAllocator](#tilde-makeallocator) | Деинициализирует текущий экземпляр `MakeAllocator` класса.

### <a name="public-methods"></a>Открытые методы

Имя                                 | Описание
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[MakeAllocator::Allocate](#allocate) | Выделяет память и связывает его с текущим `MakeAllocator` объекта.
[MakeAllocator::Detach](#detach)     | Отменяет связь памяти, выделенной с помощью [выделения](#allocate) метод из текущего `MakeAllocator` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`MakeAllocator`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="allocate"></a>MakeAllocator::Allocate

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>Возвращаемое значение

Если операция завершилась успешно, представляет указатель на выделенную память; в противном случае — значение `nullptr`.

### <a name="remarks"></a>Примечания

Выделяет память и связывает его с текущим `MakeAllocator` объекта.

Размер выделенной памяти равен размеру типа, указанного текущим `MakeAllocator` параметр шаблона.

Разработчику необходимо переопределить только `Allocate()` метод для реализации другой модели выделения памяти.

## <a name="detach"></a>MakeAllocator::Detach

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>Примечания

Отменяет связь памяти, выделенной с помощью [выделения](#allocate) метод из текущего `MakeAllocator` объекта.

При вызове метода `Detach()`, вы несете ответственность за удаление памяти, предоставляемые `Allocate` метод.

## <a name="makeallocator"></a>MakeAllocator::MakeAllocator

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
MakeAllocator();
```

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `MakeAllocator`.

## <a name="tilde-makeallocator"></a>MakeAllocator:: ~ MakeAllocator

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>Примечания

Деинициализирует текущий экземпляр `MakeAllocator` класса.

Этот деструктор также удаляет базовой выделенную память при необходимости.
