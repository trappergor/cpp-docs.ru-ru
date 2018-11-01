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
ms.openlocfilehash: 4f706b4551d71c77e136e4d65d2d6a3183293d8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454500"
---
# <a name="singlelinkregistry-class"></a>Класс single_link_registry

Объект `single_link_registry` представляет собой `network_link_registry`, управляющий только одним блоком источника или целевым блоком.

## <a name="syntax"></a>Синтаксис

```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

#### <a name="parameters"></a>Параметры

*_Block*<br/>
Тип блока данных, хранящихся в `single_link_registry` объекта.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[single_link_registry](#ctor)|Создает объект `single_link_registry`.|
|[~ single_link_registry деструктор](#dtor)|Уничтожает `single_link_registry` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[add](#add)|Добавляет ссылку на `single_link_registry` объекта. (Переопределяет [network_link_registry::add](network-link-registry-class.md#add).)|
|[begin](#begin)|Возвращает итератор, указывающий на первый элемент в `single_link_registry` объекта. (Переопределяет [network_link_registry::begin](network-link-registry-class.md#begin).)|
|[Содержит](#contains)|Поиск `single_link_registry` объекта для указанного блока. (Переопределяет [network_link_registry::contains](network-link-registry-class.md#contains).)|
|[count](#count)|Подсчитывает количество элементов в `single_link_registry` объекта. (Переопределяет [network_link_registry::count](network-link-registry-class.md#count).)|
|[remove](#remove)|Удаляет ссылку из `single_link_registry` объекта. (Переопределяет [network_link_registry::remove](network-link-registry-class.md#remove).)|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="add"></a> Добавить

Добавляет ссылку на `single_link_registry` объекта.

```
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Связать*<br/>
Указатель на блок для добавления.

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_link_target](invalid-link-target-class.md) исключение, если уже существует ссылка в данном реестре.

##  <a name="begin"></a> начать

Возвращает итератор, указывающий на первый элемент в `single_link_registry` объекта.

```
virtual iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, адресующий первый элемент в `single_link_registry` объекта.

### <a name="remarks"></a>Примечания

Конечное состояние обозначается `NULL` ссылку.

##  <a name="contains"></a> Содержит

Поиск `single_link_registry` объекта для указанного блока.

```
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Связать*<br/>
Указатель на блок, который необходимо найти в `single_link_registry` объекта.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** ссылку, если было обнаружено **false** в противном случае.

##  <a name="count"></a> число

Подсчитывает количество элементов в `single_link_registry` объекта.

```
virtual size_t count();
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в `single_link_registry` объекта.

##  <a name="remove"></a> удалить

Удаляет ссылку из `single_link_registry` объекта.

```
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Связать*<br/>
Указатель на блок удалены, если найден.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если ссылки был найден и удален, **false** в противном случае.

##  <a name="ctor"></a> single_link_registry

Создает объект `single_link_registry`.

```
single_link_registry();
```

##  <a name="dtor"></a> ~ single_link_registry

Уничтожает `single_link_registry` объекта.

```
virtual ~single_link_registry();
```

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_operation](invalid-operation-class.md) исключение, если он вызывается до удаления ссылки.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс multi_link_registry](multi-link-registry-class.md)
