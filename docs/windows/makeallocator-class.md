---
title: Makeallocator-класс | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
- implements/Microsoft::WRL::Details::MakeAllocator::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::MakeAllocator class
- Microsoft::WRL::Details::MakeAllocator::Allocate method
- Microsoft::WRL::Details::MakeAllocator::Detach method
- Microsoft::WRL::Details::MakeAllocator::MakeAllocator, constructor
- Microsoft::WRL::Details::MakeAllocator::~MakeAllocator, destructor
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 94c094fe21127592bd8756d0f0b467e2c74df487
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789245"
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
`true` выделить память для объекта, который поддерживает слабых ссылок; `false` выделить память для объекта, который не поддерживает слабые ссылки.

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

**Пространство имен:** Microsoft::wrl:: Details

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
