---
title: Класс allocator_base | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_base
- allocators/stdext::allocators::allocator_base
- allocators/stdext::allocator_base::const_pointer
- allocators/stdext::allocator_base::const_reference
- allocators/stdext::allocator_base::difference_type
- allocators/stdext::allocator_base::pointer
- allocators/stdext::allocator_base::reference
- allocators/stdext::allocator_base::size_type
- allocators/stdext::allocator_base::value_type
- allocators/stdext::allocator_base::_Charalloc
- allocators/stdext::allocator_base::_Chardealloc
- allocators/stdext::allocator_base::address
- allocators/stdext::allocator_base::allocate
- allocators/stdext::allocator_base::construct
- allocators/stdext::allocator_base::deallocate
- allocators/stdext::allocator_base::destroy
- allocators/stdext::allocator_base::max_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocator_base [C++]
- stdext::allocators [C++], allocator_base
- stdext::allocator_base [C++], const_pointer
- stdext::allocator_base [C++], const_reference
- stdext::allocator_base [C++], difference_type
- stdext::allocator_base [C++], pointer
- stdext::allocator_base [C++], reference
- stdext::allocator_base [C++], size_type
- stdext::allocator_base [C++], value_type
- stdext::allocator_base [C++], _Charalloc
- stdext::allocator_base [C++], _Chardealloc
- stdext::allocator_base [C++], address
- stdext::allocator_base [C++], allocate
- stdext::allocator_base [C++], construct
- stdext::allocator_base [C++], deallocate
- stdext::allocator_base [C++], destroy
- stdext::allocator_base [C++], max_size
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c078933ad35cff1a52de433b1ae5d321db1985c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847784"
---
# <a name="allocatorbase-class"></a>Класс allocator_base

Определяет базовый класс и общие функции, необходимые для создания определяемого пользователем распределителя из фильтра синхронизации.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type, class Sync>
class allocator_base
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`Type`|Тип элементов, распределяемых распределителем.|
|`Sync`|Политика синхронизации распределителя: [класс sync_none](../standard-library/sync-none-class.md), [класс sync_per_container](../standard-library/sync-per-container-class.md), [класс sync_per_thread](../standard-library/sync-per-thread-class.md) или [класс sync_shared](../standard-library/sync-shared-class.md).|

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[allocator_base](#allocator_base)|Создает объект типа `allocator_base`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[const_pointer](#const_pointer)|Тип, предоставляющий постоянный указатель на тип объекта, управляемого распределителем.|
|[const_reference](#const_reference)|Тип, предоставляющий постоянную ссылку на тип объекта, управляемого распределителем.|
|[difference_type](#difference_type)|Тип целого числа со знаком, который может представлять разницу между значениями указателей на тип объекта, управляемого распределителем.|
|[pointer](#pointer)|Тип, предоставляющий указатель на тип объекта, управляемого распределителем.|
|[reference](#reference)|Тип, предоставляющий ссылку на тип объекта, управляемого распределителем.|
|[size_type](#size_type)|Тип целого числа без знака, который может представлять длину любой последовательности, которую объект класса шаблона `allocator_base` может выделить.|
|[value_type](#value_type)|Тип, управляемый распределителем.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[_Charalloc](#charalloc)|Выделяет память для массива типа `char`.|
|[_Chardealloc](#chardealloc)|Освобождает хранилище для массива, содержащего элементы типа `char`.|
|[address](#address)|Находит адрес объекта, значение которого задано.|
|[allocate](#allocate)|Выделяет блок памяти, достаточный для хранения по крайней мере некоторого указанного числа элементов.|
|[construct](#construct)|Создает определенный тип объекта по указанному адресу, инициализированный с использованием заданного значения.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[destroy](#destroy)|Вызывает деструктор объектов без освобождения памяти, в которой хранился объект.|
|[max_size](#max_size)|Возвращает количество элементов типа `Type`, которые могут быть выделены объектом класса в пределах имеющейся свободной памяти.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="charalloc"></a>  allocator_base::_Charalloc

Выделяет память для массива типа `char`.

```cpp
char *_Charalloc(size_type count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`count`|Число элементов в массиве, которые нужно выделить.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Примечания

Эта функция-член используется контейнерами при компиляции с компилятором, которому не удается скомпилировать повторную привязку. Она реализует `_Charalloc` для пользовательского распределителя, возвращая результат вызова функции `allocate` фильтра синхронизации.

## <a name="chardealloc"></a>  allocator_base::_Chardealloc

Освобождает хранилище для массива, содержащего элементы типа `char`.

```cpp
void _Chardealloc(void* ptr, size_type count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`ptr`|Указатель на первый объект, который необходимо освободить из хранилища.|
|`count`|Количество объектов для освобождения из хранилища.|

### <a name="remarks"></a>Примечания

Эта функция-член используется контейнерами при компиляции с компилятором, которому не удается скомпилировать повторную привязку. Она реализует `_Chardealloc` для пользовательского распределителя путем вызова функции `deallocate` фильтра синхронизации. Указатель ptr должен быть возвращен ранее путем вызова `_Charalloc`allocator, который сравнивает его с `*this`, выделяя объект массива того же типа и размера. `_Chardealloc` никогда не создает исключений.

## <a name="address"></a>  allocator_base::address

Находит адрес объекта, значение которого задано.

```cpp
pointer address(reference val);

const_pointer address(const_reference val);
```

### <a name="parameters"></a>Параметры

`val` Значение const или nonconst, адрес которого осуществляется для объекта.

### <a name="return-value"></a>Возвращаемое значение

Константный или неконстантный указатель на найденный объект соответственно константного или неконстантного значения.

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем возврата `&val`.

## <a name="allocate"></a>  allocator_base::allocate

Выделяет блок памяти, достаточный для хранения по крайней мере некоторого указанного числа элементов.

```cpp
template <class Other>
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`_Nx`|Число выделяемых элементов в массиве.|
|`_Hint`|Этот параметр не учитывается.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Примечания

Эта функция-член реализует выделение памяти для пользовательского распределителя путем возврата результата вызова функции `allocate` фильтра синхронизации типа Type `*`, если `_Nx == 1`, в противном случае — путем возврата результата вызова приведения `operator new(_Nx * sizeof(Type))` к типу Type `*`.

## <a name="allocator_base"></a>  allocator_base::allocator_base

Создает объект типа `allocator_base`.

```cpp
allocator_base();

template <class Other>
allocator_base(const allocator_base<Other, Sync>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`right`|Объект allocator для копирования.|

### <a name="remarks"></a>Примечания

Первый конструктор создает экземпляр [allocator_base](../standard-library/allocator-base-class.md). Второй конструктор создает экземпляр `allocator_base` так, что для любого экземпляра `allocator_base<Type, _Sync>` `a`, `allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a`.

## <a name="const_pointer"></a>  allocator_base::const_pointer

Тип, предоставляющий постоянный указатель на тип объекта, управляемого распределителем.

```cpp
typedef const Type *const_pointer;
```

## <a name="const_reference"></a>  allocator_base::const_reference

Тип, предоставляющий постоянную ссылку на тип объекта, управляемого распределителем.

```cpp
typedef const Type& const_reference;
```

## <a name="construct"></a>  allocator_base::construct

Создает определенный тип объекта по указанному адресу, инициализированный с использованием заданного значения.

```cpp
void construct(pointer ptr, const Type& val);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`ptr`|Указатель места, в котором должен создаваться объект.|
|`val`|Значение, с которым создаваемый объект будет инициализирован.|

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем вызова `new((void*)ptr Type(val)`.

## <a name="deallocate"></a>  allocator_base::deallocate

Освобождает указанное число объектов из памяти, начиная с заданной позиции.

```cpp
void deallocate(pointer ptr, size_type _Nx);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`ptr`|Указатель на первый объект, который необходимо освободить из хранилища.|
|`_Nx`|Количество объектов для освобождения из хранилища.|

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем вызова `deallocate(ptr)` в фильтре синхронизации `Sync`, если `_Nx == 1`, в противном случае — путем вызова `operator delete(_Nx * ptr)`.

## <a name="destroy"></a>  allocator_base::destroy

Вызывает деструктор объектов без освобождения памяти, в которой хранился объект.

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`ptr`|Указатель, обозначающий адрес уничтожаемого объекта.|

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем вызова `ptr->~Type()`.

## <a name="difference_type"></a>  allocator_base::difference_type

Тип целого числа со знаком, который может представлять разницу между значениями указателей на тип объекта, управляемого распределителем.

```cpp
typedef std::ptrdiff_t difference_type;
```

## <a name="max_size"></a>  allocator_base::max_size

Возвращает количество элементов типа `Type`, которые могут быть выделены объектом класса в пределах имеющейся свободной памяти.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, которые могут быть выделены.

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем возврата `(size_t)-1 / sizeof(Type)`, если `0 < (size_t)-1 / sizeof(Type)`в противном случае — `1`.

## <a name="pointer"></a>  allocator_base::pointer

Тип, предоставляющий указатель на тип объекта, управляемого распределителем.

```cpp
typedef Type *pointer;
```

## <a name="reference"></a>  allocator_base::reference

Тип, предоставляющий ссылку на тип объекта, управляемого распределителем.

```cpp
typedef Type& reference;
```

## <a name="size_type"></a>  allocator_base::size_type

Тип целого числа без знака, который может представлять длину любой последовательности, которую объект класса шаблона `allocator_base` может выделить.

```cpp
typedef std::size_t size_type;
```

## <a name="value_type"></a>  allocator_base::value_type

Тип, управляемый распределителем.

```cpp
typedef Type value_type;
```

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
