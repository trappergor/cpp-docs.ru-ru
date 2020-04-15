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
ms.openlocfilehash: dc0d83f2550646572a4eff2bec7850037c6dbf6a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371325"
---
# <a name="makeallocator-class"></a>MakeAllocator - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

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

*имеетСлабыйСправкаПоддержка*<br/>
**верно** для выделения памяти для объекта, который поддерживает слабые ссылки; **ложное** выделение памяти для объекта, не поддерживающего слабые ссылки.

## <a name="remarks"></a>Remarks

Выделяет память для активируемый класс, с или без слабой поддержки ссылки.

Переопределить `MakeAllocator` класс для реализации модели распределения памяти, определяемой пользователем.

`MakeAllocator`обычно используется для предотвращения утечек памяти, если объект бросает во время строительства.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                  | Описание
----------------------------------------------------- | ----------------------------------------------------------------
[MakeAllocator::MakeAllocator](#makeallocator)        | Инициализирует новый экземпляр класса `MakeAllocator`.
[MakeAllocator::](#tilde-makeallocator) | Деприиратизирует текущий `MakeAllocator` экземпляр класса.

### <a name="public-methods"></a>Открытые методы

Имя                                 | Описание
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[MakeAllocator::Выделение](#allocate) | Распределяет память и связывает ее `MakeAllocator` с текущим объектом.
[MakeAllocator::Detach](#detach)     | Отсажает память, выделенную методом [Выделения](#allocate) из текущего `MakeAllocator` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`MakeAllocator`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="makeallocatorallocate"></a><a name="allocate"></a>MakeAllocator::Выделение

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>Возвращаемое значение

Если операция завершилась успешно, представляет указатель на выделенную память; в противном случае — значение `nullptr`.

### <a name="remarks"></a>Remarks

Распределяет память и связывает ее `MakeAllocator` с текущим объектом.

Размер выделенной памяти — это размер типа, `MakeAllocator` указанный текущим параметром шаблона.

Разработчику необходимо переопределить `Allocate()` только метод для реализации другой модели распределения памяти.

## <a name="makeallocatordetach"></a><a name="detach"></a>MakeAllocator::Detach

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>Remarks

Отсажает память, выделенную методом [Выделения](#allocate) из текущего `MakeAllocator` объекта.

Если вы `Detach()`звоните, вы несете ответственность за `Allocate` удаляем память, предоставляемую методом.

## <a name="makeallocatormakeallocator"></a><a name="makeallocator"></a>MakeAllocator::MakeAllocator

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
MakeAllocator();
```

### <a name="remarks"></a>Remarks

Инициализирует новый экземпляр класса `MakeAllocator`.

## <a name="makeallocatormakeallocator"></a><a name="tilde-makeallocator"></a>MakeAllocator::

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>Remarks

Деприиратизирует текущий `MakeAllocator` экземпляр класса.

Этот деструктор также удаляет базовую выделенную память, если это необходимо.
