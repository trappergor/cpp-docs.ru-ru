---
title: Класс single_link_registry
ms.date: 11/04/2016
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
ms.openlocfilehash: c29caf6d31df316e80b15fe6827c81e34ece8a18
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142719"
---
# <a name="single_link_registry-class"></a>Класс single_link_registry

Объект `single_link_registry` представляет собой `network_link_registry`, управляющий только одним блоком источника или целевым блоком.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Параметры

*_Block*<br/>
Тип данных Block, хранящийся в объекте `single_link_registry`.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[single_link_registry](#ctor)|Формирует объект `single_link_registry`.|
|[Деструктор ~ single_link_registry](#dtor)|Уничтожает объект `single_link_registry`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[добавление](#add)|Добавляет ссылку на объект `single_link_registry`. (Переопределяет [network_link_registry:: Add](network-link-registry-class.md#add).)|
|[begin](#begin)|Возвращает итератор, который является первым элементом в объекте `single_link_registry`. (Переопределяет [network_link_registry:: Begin](network-link-registry-class.md#begin).)|
|[contains](#contains)|Выполняет поиск указанного блока в объекте `single_link_registry`. (Переопределяет [network_link_registry:: Contains](network-link-registry-class.md#contains).)|
|[count](#count)|Подсчитывает количество элементов в объекте `single_link_registry`. (Переопределяет [network_link_registry:: count](network-link-registry-class.md#count).)|
|[remove](#remove)|Удаляет ссылку из объекта `single_link_registry`. (Переопределяет [network_link_registry:: Remove](network-link-registry-class.md#remove).)|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="add"></a>включить

Добавляет ссылку на объект `single_link_registry`.

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на добавляемый блок.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_link_target](invalid-link-target-class.md) , если в этом реестре уже есть ссылка.

## <a name="begin"></a>начале

Возвращает итератор, который является первым элементом в объекте `single_link_registry`.

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, обращающийся к первому элементу в объекте `single_link_registry`.

### <a name="remarks"></a>Remarks

Конечное состояние обозначается ссылкой на `NULL`.

## <a name="contains"></a>содержащих

Выполняет поиск указанного блока в объекте `single_link_registry`.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, который необходимо найти в объекте `single_link_registry`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если ссылка найдена; в противном случае — **значение false** .

## <a name="count"></a>расчета

Подсчитывает количество элементов в объекте `single_link_registry`.

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в объекте `single_link_registry`.

## <a name="remove"></a>отменит

Удаляет ссылку из объекта `single_link_registry`.

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на удаляемый блок, если он найден.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если ссылка была найдена и удалена; в противном случае — **значение false** .

## <a name="ctor"></a>single_link_registry

Формирует объект `single_link_registry`.

```cpp
single_link_registry();
```

## <a name="dtor"></a>~ single_link_registry

Уничтожает объект `single_link_registry`.

```cpp
virtual ~single_link_registry();
```

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_operation](invalid-operation-class.md) , если оно вызывается перед удалением ссылки.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс multi_link_registry](multi-link-registry-class.md)
