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
ms.openlocfilehash: 5e90dd3b23b33f6699f2df4ce0df9178f95816b8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273260"
---
# <a name="location-class"></a>Класс location

Абстракция физического расположения на оборудовании.

## <a name="syntax"></a>Синтаксис

```
class location;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[расположение](#ctor)|Перегружен. Создает объект `location`.|
|[~ расположение деструктор](#dtor)|Уничтожает объект `location`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Текущий](#current)|Возвращает объект `location`, представляющий наиболее определенное расположение, выполняемое вызывающим потоком.|
|[from_numa_node](#from_numa_node)|Возвращает объект `location`, представляющий заданный узел NUMA.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[operator!=](#operator_neq)|Определяет, представляют ли два объекта `location` различные расположения.|
|[оператор=](#operator_eq)|Назначает содержимое другого объекта `location` данному.|
|[operator==](#operator_eq_eq)|Определяет, является ли два `location` объекты представляют то же расположение.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`location`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="dtor"></a> ~ расположение

Уничтожает объект `location`.

```
~location();
```

##  <a name="current"></a> Текущий

Возвращает объект `location`, представляющий наиболее определенное расположение, выполняемое вызывающим потоком.

```
static location __cdecl current();
```

### <a name="return-value"></a>Возвращаемое значение

Расположение, представляющее наиболее определенное место, выполняемое вызывающим потоком.

##  <a name="from_numa_node"></a> from_numa_node

Возвращает объект `location`, представляющий заданный узел NUMA.

```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>Параметры

*_NumaNodeNumber*<br/>
Номер узла NUMA для построения его расположения.

### <a name="return-value"></a>Возвращаемое значение

Расположение, представляющее узел NUMA, указывается с помощью параметра `_NumaNodeNumber`.

##  <a name="ctor"></a> расположение

Создает объект `location`.

```
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
(Необязательно) Указатель привязки.

### <a name="remarks"></a>Примечания

Созданное расположение по умолчанию представляет систему в целом.

##  <a name="operator_neq"></a> оператор! =

Определяет, представляют ли два объекта `location` различные расположения.

```
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Операнд `location`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если расположения различаются, **false** в противном случае.

##  <a name="operator_eq"></a> оператор =

Назначает содержимое другого объекта `location` данному.

```
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Исходный объект `location`.

### <a name="return-value"></a>Возвращаемое значение

##  <a name="operator_eq_eq"></a> оператор ==

Определяет, является ли два `location` объекты представляют то же расположение.

```
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Операнд `location`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если этих двух папок совпадают, и **false** в противном случае.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
