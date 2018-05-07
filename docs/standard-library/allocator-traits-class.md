---
title: Класс allocator_traits | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- memory/std::allocator_traits
- memory/std::allocator_traits::propagate_on_container_move_assignment
- memory/std::allocator_traits::const_pointer
- memory/std::allocator_traits::propagate_on_container_swap
- memory/std::allocator_traits::propagate_on_container_copy_assignment
- memory/std::allocator_traits::difference_type
- memory/std::allocator_traits::allocator_type
- memory/std::allocator_traits::value_type
- memory/std::allocator_traits::pointer
- memory/std::allocator_traits::size_type
- memory/std::allocator_traits::const_void_pointer
- memory/std::allocator_traits::void_pointer
- memory/std::allocator_traits::allocate
- memory/std::allocator_traits::construct
- memory/std::allocator_traits::deallocate
- memory/std::allocator_traits::destroy
- memory/std::allocator_traits::max_size
- memory/std::allocator_traits::select_on_container_copy_construction
dev_langs:
- C++
ms.assetid: 612974b8-b5d4-4668-82fb-824bff6821d6
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::allocator_traits [C++]
- std::allocator_traits [C++], propagate_on_container_move_assignment
- std::allocator_traits [C++], const_pointer
- std::allocator_traits [C++], propagate_on_container_swap
- std::allocator_traits [C++], propagate_on_container_copy_assignment
- std::allocator_traits [C++], difference_type
- std::allocator_traits [C++], allocator_type
- std::allocator_traits [C++], value_type
- std::allocator_traits [C++], pointer
- std::allocator_traits [C++], size_type
- std::allocator_traits [C++], const_void_pointer
- std::allocator_traits [C++], void_pointer
- std::allocator_traits [C++], allocate
- std::allocator_traits [C++], construct
- std::allocator_traits [C++], deallocate
- std::allocator_traits [C++], destroy
- std::allocator_traits [C++], max_size
- std::allocator_traits [C++], select_on_container_copy_construction
ms.workload:
- cplusplus
ms.openlocfilehash: 8e95f203cfc59d21056119701f56eb4a0084bcce
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="allocatortraits-class"></a>Класс allocator_traits

Класс шаблона описывает объект, который дополняет *тип распределителя*. Тип распределителя — это любой тип, описывающий объект allocator, который используется для управления выделенной памятью. В частности, для любого типа распределителя `Alloc` можно использовать `allocator_traits<Alloc>`, чтобы определить все сведения, необходимые контейнеру с распределителем. Дополнительные сведения см. в разделе [Класс allocator](../standard-library/allocator-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Alloc>
class allocator_traits;
```

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|----------|-----------------|
|`allocator_traits::allocator_type`|Этот тип является синонимом для параметра-шаблона `Alloc`.|
|`allocator_traits::const_pointer`|Этот тип — `Alloc::const_pointer`, если он правильно сформирован; в противном случае этот тип — `pointer_traits<pointer>::rebind<const value_type>`.|
|`allocator_traits::const_void_pointer`|Этот тип — `Alloc::const_void_pointer`, если он правильно сформирован; в противном случае этот тип — `pointer_traits<pointer>::rebind<const void>`.|
|`allocator_traits::difference_type`|Этот тип — `Alloc::difference_type`, если он правильно сформирован; в противном случае этот тип — `pointer_traits<pointer>::difference_type`.|
|`allocator_traits::pointer`|Этот тип — `Alloc::pointer`, если он правильно сформирован; в противном случае этот тип — `value_type *`.|
|`allocator_traits::propagate_on_container_copy_assignment`|Этот тип — `Alloc::propagate_on_container_copy_assignment`, если он правильно сформирован; в противном случае этот тип — `false_type`.|
|`allocator_traits::propagate_on_container_move_assignment`|Этот тип — `Alloc::propagate_on_container_move_assignment`, если он правильно сформирован; в противном случае этот тип — `false_type`. Если тип содержит значение true, контейнер с поддержкой распределителя копирует его сохраненный распределитель для назначения перемещения.|
|`allocator_traits::propagate_on_container_swap`|Этот тип — `Alloc::propagate_on_container_swap`, если он правильно сформирован; в противном случае этот тип — `false_type`. Если тип содержит значение true, контейнер с поддержкой распределителя копирует его сохраненный распределитель в перестановку.|
|`allocator_traits::size_type`|Этот тип — `Alloc::size_type`, если он правильно сформирован; в противном случае этот тип — `make_unsigned<difference_type>::type`.|
|`allocator_traits::value_type`|Этот тип является синонимом `Alloc::value_type`.|
|`allocator_traits::void_pointer`|Этот тип — `Alloc::void_pointer`, если он правильно сформирован; в противном случае этот тип — `pointer_traits<pointer>::rebind<void>`.|

### <a name="static-methods"></a>Статические методы

Следующие статические методы вызывают соответствующий метод в указанном параметре распределителя.

|name|Описание|
|----------|-----------------|
|[allocate](#allocate)|Статический метод, который выделяет память с помощью указанного параметра распределителя.|
|[construct](#construct)|Статический метод, который используется указанным распределителем для создания объекта.|
|[deallocate](#deallocate)|Статический метод, который используется указанным распределителем для освобождения указанного количества объектов.|
|[destroy](#destroy)|Статический метод, который используется указанным распределителем для вызова деструктора в объекте без освобождения его памяти.|
|[max_size](#max_size)|Статический метод, который используется указанным распределителем, чтобы определить максимальное число объектов, которые могут быть распределены.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Статический метод, который вызывает `select_on_container_copy_construction` в указанном распределителе.|

## <a name="requirements"></a>Требования

**Заголовок:** \<memory>

**Пространство имен:** std

## <a name="allocate"></a>  allocator_traits::allocate

Статический метод, который выделяет память с помощью указанного параметра распределителя.

```cpp
static pointer allocate(Alloc& al, size_type count);

static pointer allocate(Alloc& al, size_type count,
    typename allocator_traits<void>::const_pointer* hint);
```

### <a name="parameters"></a>Параметры

`al` Объект распределителя.

`count` Количество элементов для выделения.

`hint` Объект `const_pointer` , может помочь объект распределителя в выполнении запроса для хранения, найдя адрес выделенного объекта до запроса. Пустой указатель рассматривается как отсутствие подсказки.

### <a name="return-value"></a>Возвращаемое значение

Каждый метод возвращает указатель на выделенный объект.

Первый статический метод возвращает `al.allocate(count)`.

Второй метод возвращает `al.allocate(count, hint)`, если это выражение правильно сформировано; в противном случае возвращается `al.allocate(count)`.

## <a name="construct"></a>  allocator_traits::construct

Статический метод, который используется указанным распределителем для создания объекта.

```cpp
template <class Uty, class Types>
static void construct(Alloc& al, Uty* ptr, Types&&... args);
```

### <a name="parameters"></a>Параметры

`al` Объект распределителя.

`ptr` Указатель на расположение, где будет создаваться объект.

`args` Список аргументов, который передается в конструктор объекта.

### <a name="remarks"></a>Примечания

Эта статическая функция-член вызывает `al.construct(ptr, args...)`, если выражение правильно сформировано; в противном случае оно оценивается как `::new (static_cast<void *>(ptr)) Uty(std::forward<Types>(args)...)`.

## <a name="deallocate"></a>  allocator_traits::DEALLOCATE

Статический метод, который используется указанным распределителем для освобождения указанного количества объектов.

```cpp
static void deallocate(Alloc al,
    pointer ptr,
    size_type count);
```

### <a name="parameters"></a>Параметры

`al` Объект распределителя.

`ptr` Указатель начальной позиции освобождение объектов.

`count` Количество объектов для освобождения.

### <a name="remarks"></a>Примечания

Этот метод вызывает `al.deallocate(ptr, count)`.

Этот метод ничего не создает.

## <a name="destroy"></a>  allocator_traits::destroy

Статический метод, который используется указанным распределителем для вызова деструктора в объекте без освобождения его памяти.

```cpp
template <class Uty>
static void destroy(Alloc& al, Uty* ptr);
```

### <a name="parameters"></a>Параметры

`al` Объект распределителя.

`ptr` Указатель на расположение объекта.

### <a name="remarks"></a>Примечания

Этот метод вызывает `al.destroy(ptr)`, если выражение правильно сформировано; в противном случае оно оценивается как `ptr->~Uty()`.

## <a name="max_size"></a>  allocator_traits::max_size

Статический метод, который используется указанным распределителем, чтобы определить максимальное число объектов, которые могут быть распределены.

```cpp
static size_type max_size(const Alloc& al);
```

### <a name="parameters"></a>Параметры

`al` Объект распределителя.

### <a name="remarks"></a>Примечания

Этот метод возвращает `al.max_size()`, если это выражение правильно сформировано; в противном случае возвращается `numeric_limits<size_type>::max()`.

## <a name="select_on_container_copy_construction"></a>  allocator_traits::select_on_container_copy_construction

Статический метод, который вызывает `select_on_container_copy_construction` в указанном распределителе.

```cpp
static Alloc select_on_container_copy_construction(const Alloc& al);
```

### <a name="parameters"></a>Параметры

`al` Объект распределителя.

### <a name="return-value"></a>Возвращаемое значение

Данный метод возвращает `al.select_on_container_copy_construction()`, если этот тип правильно сформирован; в противном случае возвращается `al`.

### <a name="remarks"></a>Примечания

Этот метод используется для указания распределителя при создании копии связанного контейнера.

## <a name="see-also"></a>См. также

[\<memory>](../standard-library/memory.md)<br/>
[Структура pointer_traits](../standard-library/pointer-traits-struct.md)<br/>
[Класс scoped_allocator_adaptor](../standard-library/scoped-allocator-adaptor-class.md)<br/>
