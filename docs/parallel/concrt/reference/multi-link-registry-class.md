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
ms.openlocfilehash: e22df5ee65d0219a46065044385dca46aac297a3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142373"
---
# <a name="multi_link_registry-class"></a>Класс multi_link_registry

Объект `multi_link_registry` представляет собой `network_link_registry`, управляющий несколькими блоками источников или целевыми блоками.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Параметры

*_Block*<br/>
Тип данных Block, хранящийся в объекте `multi_link_registry`.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[multi_link_registry](#ctor)|Формирует объект `multi_link_registry`.|
|[Деструктор ~ multi_link_registry](#dtor)|Уничтожает объект `multi_link_registry`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[добавление](#add)|Добавляет ссылку на объект `multi_link_registry`. (Переопределяет [network_link_registry:: Add](network-link-registry-class.md#add).)|
|[begin](#begin)|Возвращает итератор, который является первым элементом в объекте `multi_link_registry`. (Переопределяет [network_link_registry:: Begin](network-link-registry-class.md#begin).)|
|[contains](#contains)|Выполняет поиск указанного блока в объекте `multi_link_registry`. (Переопределяет [network_link_registry:: Contains](network-link-registry-class.md#contains).)|
|[count](#count)|Подсчитывает количество элементов в объекте `multi_link_registry`. (Переопределяет [network_link_registry:: count](network-link-registry-class.md#count).)|
|[remove](#remove)|Удаляет ссылку из объекта `multi_link_registry`. (Переопределяет [network_link_registry:: Remove](network-link-registry-class.md#remove).)|
|[set_bound](#set_bound)|Задает верхнюю границу числа ссылок, которые может содержать объект `multi_link_registry`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="add"></a>включить

Добавляет ссылку на объект `multi_link_registry`.

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на добавляемый блок.

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_link_target](invalid-link-target-class.md) , если ссылка уже имеется в реестре, или если привязка уже была задана с помощью функции `set_bound` и ссылка была удалена с момента удаления.

## <a name="begin"></a>начале

Возвращает итератор, который является первым элементом в объекте `multi_link_registry`.

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, обращающийся к первому элементу в объекте `multi_link_registry`.

### <a name="remarks"></a>Remarks

Конечное состояние обозначается ссылкой на `NULL`.

## <a name="contains"></a>содержащих

Выполняет поиск указанного блока в объекте `multi_link_registry`.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, который необходимо найти в объекте `multi_link_registry`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если указанный блок найден; в противном случае — **значение false** .

## <a name="count"></a>расчета

Подсчитывает количество элементов в объекте `multi_link_registry`.

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в объекте `multi_link_registry`.

## <a name="ctor"></a>multi_link_registry

Формирует объект `multi_link_registry`.

```cpp
multi_link_registry();
```

## <a name="dtor"></a>~ multi_link_registry

Уничтожает объект `multi_link_registry`.

```cpp
virtual ~multi_link_registry();
```

### <a name="remarks"></a>Remarks

Метод вызывает исключение [invalid_operation](invalid-operation-class.md) , если вызывается до удаления всех ссылок.

## <a name="remove"></a>отменит

Удаляет ссылку из объекта `multi_link_registry`.

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на удаляемый блок, если он найден.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если ссылка была найдена и удалена; в противном случае — **значение false** .

## <a name="set_bound"></a>set_bound

Задает верхнюю границу числа ссылок, которые может содержать объект `multi_link_registry`.

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Параметры

*_MaxLinks*<br/>
Максимальное число ссылок, которые может содержать объект `multi_link_registry`.

### <a name="remarks"></a>Remarks

После установки границы отсоединение записи приведет к тому, что объект `multi_link_registry` войдет в неизменяемое состояние, где дальнейшие вызовы `add` создадут исключение `invalid_link_target`.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс single_link_registry](single-link-registry-class.md)
