---
title: Класс location
ms.date: 11/04/2016
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
ms.openlocfilehash: 7f45ff6d3092bd7c27e81adddca72c9411f752d1
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139828"
---
# <a name="location-class"></a>Класс location

Абстракция физического расположения на оборудовании.

## <a name="syntax"></a>Синтаксис

```cpp
class location;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[расположение](#ctor)|Перегружен. Формирует объект `location`.|
|[Деструктор ~ Location](#dtor)|Уничтожает объект `location`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[данном](#current)|Возвращает объект `location`, представляющий наиболее определенное расположение, выполняемое вызывающим потоком.|
|[from_numa_node](#from_numa_node)|Возвращает объект `location`, представляющий заданный узел NUMA.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[operator!=](#operator_neq)|Определяет, представляют ли два объекта `location` различные расположения.|
|[оператор=](#operator_eq)|Назначает содержимое другого объекта `location` данному.|
|[operator==](#operator_eq_eq)|Определяет, представляют ли два `location` объектов одно и то же расположение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`location`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT. h

**Пространство имен:** concurrency

## <a name="dtor"></a>расположение ~

Уничтожает объект `location`.

```cpp
~location();
```

## <a name="current"></a>данном

Возвращает объект `location`, представляющий наиболее определенное расположение, выполняемое вызывающим потоком.

```cpp
static location __cdecl current();
```

### <a name="return-value"></a>Возвращаемое значение

Расположение, представляющее наиболее определенное место, выполняемое вызывающим потоком.

## <a name="from_numa_node"></a>from_numa_node

Возвращает объект `location`, представляющий заданный узел NUMA.

```cpp
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>Параметры

*_NumaNodeNumber*<br/>
Номер узла NUMA для построения его расположения.

### <a name="return-value"></a>Возвращаемое значение

Расположение, представляющее узел NUMA, указывается с помощью параметра `_NumaNodeNumber`.

## <a name="ctor"></a>места

Формирует объект `location`.

```cpp
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>

*_LocationType*<br/>

*_Id*<br/>

*_BindingId*<br/>

*_PBinding*<br/>
Используемых Указатель привязки.

### <a name="remarks"></a>Remarks

Созданное расположение по умолчанию представляет систему в целом.

## <a name="operator_neq"></a>operator! =

Определяет, представляют ли два объекта `location` различные расположения.

```cpp
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
`location`операнда.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если два расположения различаются; в противном случае — **значение false** .

## <a name="operator_eq"></a>Оператор =

Назначает содержимое другого объекта `location` данному.

```cpp
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Исходный объект `location`.

### <a name="return-value"></a>Возвращаемое значение

## <a name="operator_eq_eq"></a>Оператор = =

Определяет, представляют ли два `location` объектов одно и то же расположение.

```cpp
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
`location`операнда.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если два расположения идентичны, и **false** в противном случае.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
