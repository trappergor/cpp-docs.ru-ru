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
ms.openlocfilehash: 430190c11ec06a4f26eb9d8c4237552848420ad7
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138893"
---
# <a name="network_link_registry-class"></a>Класс network_link_registry

Абстрактный базовый класс `network_link_registry` управляет связями между блоками источников и целевыми блоками.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _Block>
class network_link_registry;
```

### <a name="parameters"></a>Параметры

*_Block*<br/>
Тип данных блока, хранящийся в `network_link_registry`.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Description|
|----------|-----------------|
|`const_pointer`|Тип, предоставляющий указатель на элемент `const` в объекте `network_link_registry`.|
|`const_reference`|Тип, предоставляющий ссылку на элемент `const`, хранящийся в объекте `network_link_registry`, для чтения и выполнения операций const.|
|`iterator`|Тип, предоставляющий итератор, который может считывать или изменять любой элемент объекта `network_link_registry`.|
|`type`|Тип, представляющий тип блока, хранящегося в объекте `network_link_registry`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[добавление](#add)|При переопределении в производном классе добавляет ссылку на объект `network_link_registry`.|
|[begin](#begin)|При переопределении в производном классе возвращает итератор на первый элемент в объекте `network_link_registry`.|
|[contains](#contains)|При переопределении в производном классе выполняет поиск указанного блока в объекте `network_link_registry`.|
|[count](#count)|При переопределении в производном классе возвращает количество элементов в объекте `network_link_registry`.|
|[remove](#remove)|При переопределении в производном классе удаляет указанный блок из объекта `network_link_registry`.|

## <a name="remarks"></a>Remarks

`network link registry` не является надежным для параллельного доступа.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`network_link_registry`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="add"></a>включить

При переопределении в производном классе добавляет ссылку на объект `network_link_registry`.

```cpp
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на добавляемый блок.

## <a name="begin"></a>начале

При переопределении в производном классе возвращает итератор на первый элемент в объекте `network_link_registry`.

```cpp
virtual iterator begin() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, обращающийся к первому элементу в объекте `network_link_registry`.

### <a name="remarks"></a>Remarks

Конечное состояние итератора обозначается ссылкой на `NULL`.

## <a name="contains"></a>содержащих

При переопределении в производном классе выполняет поиск указанного блока в объекте `network_link_registry`.

```cpp
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, поиск которого выполняется в объекте `network_link_registry`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если блок найден; в противном случае — **значение false** .

## <a name="count"></a>расчета

При переопределении в производном классе возвращает количество элементов в объекте `network_link_registry`.

```cpp
virtual size_t count() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в объекте `network_link_registry`.

## <a name="remove"></a>отменит

При переопределении в производном классе удаляет указанный блок из объекта `network_link_registry`.

```cpp
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на удаляемый блок, если он найден.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если ссылка была найдена и удалена; в противном случае — **значение false** .

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс single_link_registry](single-link-registry-class.md)<br/>
[Класс multi_link_registry](multi-link-registry-class.md)
