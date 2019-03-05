---
title: Класс network_link_registry
ms.date: 11/04/2016
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
ms.openlocfilehash: 2537ed857651b5210b104a270b3d827246b8339a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273352"
---
# <a name="networklinkregistry-class"></a>Класс network_link_registry

Абстрактный базовый класс `network_link_registry` управляет связями между блоками источников и целевыми блоками.

## <a name="syntax"></a>Синтаксис

```
template<class _Block>
class network_link_registry;
```

#### <a name="parameters"></a>Параметры

*_Block*<br/>
Тип блока данных, хранящихся в `network_link_registry`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`const_pointer`|Тип, предоставляющий указатель на `const` элемент `network_link_registry` объекта.|
|`const_reference`|Тип, предоставляющий ссылку на `const` элемент хранится в `network_link_registry` объект для чтения и выполнения операций const.|
|`iterator`|Тип, предоставляющий итератор, который может считывать или изменять любой элемент в `network_link_registry` объекта.|
|`type`|Тип, представляющий тип блока, хранящиеся в `network_link_registry` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[add](#add)|При переопределении в производном классе добавляет ссылку на `network_link_registry` объекта.|
|[begin](#begin)|При переопределении в производном классе, возвращает итератор, указывающий на первый элемент в `network_link_registry` объекта.|
|[Содержит](#contains)|При переопределении в производном классе выполняет `network_link_registry` объекта для указанного блока.|
|[count](#count)|При переопределении в производном классе возвращает число элементов в `network_link_registry` объекта.|
|[remove](#remove)|При переопределении в производном классе удаляет заданный блок из `network_link_registry` объекта.|

## <a name="remarks"></a>Примечания

`network link registry` Не является безопасным для параллельного доступа.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`network_link_registry`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="add"></a> Добавить

При переопределении в производном классе добавляет ссылку на `network_link_registry` объекта.

```
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок для добавления.

##  <a name="begin"></a> начать

При переопределении в производном классе, возвращает итератор, указывающий на первый элемент в `network_link_registry` объекта.

```
virtual iterator begin() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, адресующий первый элемент в `network_link_registry` объекта.

### <a name="remarks"></a>Примечания

Конечное состояние итератора обозначается `NULL` ссылку.

##  <a name="contains"></a> Содержит

При переопределении в производном классе выполняет `network_link_registry` объекта для указанного блока.

```
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, который ищется в `network_link_registry` объекта.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если блокировка была найдена, **false** в противном случае.

##  <a name="count"></a> число

При переопределении в производном классе возвращает число элементов в `network_link_registry` объекта.

```
virtual size_t count() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в `network_link_registry` объекта.

##  <a name="remove"></a> удалить

При переопределении в производном классе удаляет заданный блок из `network_link_registry` объекта.

```
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок удалены, если найден.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если ссылки был найден и удален, **false** в противном случае.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс single_link_registry](single-link-registry-class.md)<br/>
[Класс multi_link_registry](multi-link-registry-class.md)
