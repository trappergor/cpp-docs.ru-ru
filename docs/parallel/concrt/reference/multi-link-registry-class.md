---
title: Класс multi_link_registry
ms.date: 11/04/2016
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
ms.openlocfilehash: 388cc0082f69041368d1a444179855451d552ce6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394459"
---
# <a name="multilinkregistry-class"></a>Класс multi_link_registry

Объект `multi_link_registry` представляет собой `network_link_registry`, управляющий несколькими блоками источников или целевыми блоками.

## <a name="syntax"></a>Синтаксис

```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

#### <a name="parameters"></a>Параметры

*_Block*<br/>
Тип блока данных, хранящихся в `multi_link_registry` объекта.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[multi_link_registry](#ctor)|Создает объект `multi_link_registry`.|
|[~ multi_link_registry деструктор](#dtor)|Уничтожает `multi_link_registry` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[add](#add)|Добавляет ссылку на `multi_link_registry` объекта. (Переопределяет [network_link_registry::add](network-link-registry-class.md#add).)|
|[begin](#begin)|Возвращает итератор, указывающий на первый элемент в `multi_link_registry` объекта. (Переопределяет [network_link_registry::begin](network-link-registry-class.md#begin).)|
|[Содержит](#contains)|Поиск `multi_link_registry` объекта для указанного блока. (Переопределяет [network_link_registry::contains](network-link-registry-class.md#contains).)|
|[count](#count)|Подсчитывает количество элементов в `multi_link_registry` объекта. (Переопределяет [network_link_registry::count](network-link-registry-class.md#count).)|
|[remove](#remove)|Удаляет ссылку из `multi_link_registry` объекта. (Переопределяет [network_link_registry::remove](network-link-registry-class.md#remove).)|
|[set_bound](#set_bound)|Устанавливает верхний предел на число ссылок, `multi_link_registry` могут храниться в объекте.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="add"></a> Добавить

Добавляет ссылку на `multi_link_registry` объекта.

```
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок для добавления.

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_link_target](invalid-link-target-class.md) исключения Если ссылка уже существует в реестре или связанного уже задана `set_bound` функции и ссылки был удален.

##  <a name="begin"></a> начать

Возвращает итератор, указывающий на первый элемент в `multi_link_registry` объекта.

```
virtual iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, адресующий первый элемент в `multi_link_registry` объекта.

### <a name="remarks"></a>Примечания

Конечное состояние обозначается `NULL` ссылку.

##  <a name="contains"></a> Содержит

Поиск `multi_link_registry` объекта для указанного блока.

```
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, который необходимо найти в `multi_link_registry` объекта.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** указанного блока, если было обнаружено **false** в противном случае.

##  <a name="count"></a> число

Подсчитывает количество элементов в `multi_link_registry` объекта.

```
virtual size_t count();
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в `multi_link_registry` объекта.

##  <a name="ctor"></a> multi_link_registry

Создает объект `multi_link_registry`.

```
multi_link_registry();
```

##  <a name="dtor"></a> ~multi_link_registry

Уничтожает `multi_link_registry` объекта.

```
virtual ~multi_link_registry();
```

### <a name="remarks"></a>Примечания

Метод вызывает [invalid_operation](invalid-operation-class.md) исключение, если вызывается до удаления всех связей.

##  <a name="remove"></a> удалить

Удаляет ссылку из `multi_link_registry` объекта.

```
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок удалены, если найден.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если ссылки был найден и удален, **false** в противном случае.

##  <a name="set_bound"></a> set_bound

Устанавливает верхний предел на число ссылок, `multi_link_registry` могут храниться в объекте.

```
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Параметры

*_MaxLinks*<br/>
Максимальное число ссылок, `multi_link_registry` могут храниться в объекте.

### <a name="remarks"></a>Примечания

После установки границы отсоединение записи приведет к тому, что объект `multi_link_registry` войдет в неизменяемое состояние, где дальнейшие вызовы `add` создадут исключение `invalid_link_target`.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс single_link_registry](single-link-registry-class.md)
