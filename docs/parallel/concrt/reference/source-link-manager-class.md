---
title: Класс source_link_manager
ms.date: 11/04/2016
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
ms.openlocfilehash: 35c7cc72520cdb0675abf9c15574a49e33741d0b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142701"
---
# <a name="source_link_manager-class"></a>Класс source_link_manager

Объект `source_link_manager` управляет сетевыми соединениями блоков обмена сообщениями с блоками `ISource`.

## <a name="syntax"></a>Синтаксис

```cpp
template<class _LinkRegistry>
class source_link_manager;
```

### <a name="parameters"></a>Параметры

*_LinkRegistry*<br/>
Реестр сетевых связей.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Description|
|----------|-----------------|
|`const_pointer`|Тип, предоставляющий указатель на элемент `const` в объекте `source_link_manager`.|
|`const_reference`|Тип, предоставляющий ссылку на элемент `const`, хранящийся в объекте `source_link_manager`, для чтения и выполнения операций const.|
|`iterator`|Тип, предоставляющий итератор, который может считывать или изменять любой элемент в объекте `source_link_manager`.|
|`type`|Тип реестра ссылок, управляемого объектом `source_link_manager`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[source_link_manager](#ctor)|Формирует объект `source_link_manager`.|
|[Деструктор ~ source_link_manager](#dtor)|Уничтожает объект `source_link_manager`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[добавление](#add)|Добавляет ссылку на объект `source_link_manager`.|
|[begin](#begin)|Возвращает итератор, который является первым элементом в объекте `source_link_manager`.|
|[contains](#contains)|Выполняет поиск указанного блока в `network_link_registry` в этом `source_link_manager` объекте.|
|[count](#count)|Подсчитывает количество связанных блоков в объекте `source_link_manager`.|
|[reference](#reference)|Получает ссылку на объект `source_link_manager`.|
|[register_target_block](#register_target_block)|Регистрирует целевой блок, содержащий этот объект `source_link_manager`.|
|[release](#release)|Освобождает ссылку на объект `source_link_manager`.|
|[remove](#remove)|Удаляет ссылку из объекта `source_link_manager`.|
|[set_bound](#set_bound)|Задает максимальное число ссылок на источники, которые могут быть добавлены к этому объекту `source_link_manager`.|

## <a name="remarks"></a>Remarks

Сейчас блоки исходного кода подсчитываются. Это оболочка для объекта `network_link_registry`, который разрешает одновременный доступ к ссылкам и предоставляет возможность ссылаться на ссылки через обратные вызовы. Блоки сообщений (`target_block`s или `propagator_block`s) должны использовать этот класс для своих исходных ссылок.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`source_link_manager`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="add"></a>включить

Добавляет ссылку на объект `source_link_manager`.

```cpp
void add(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на добавляемый блок.

## <a name="begin"></a>начале

Возвращает итератор, который является первым элементом в объекте `source_link_manager`.

```cpp
iterator begin();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, обращающийся к первому элементу в объекте `source_link_manager`.

### <a name="remarks"></a>Remarks

Конечное состояние итератора обозначается ссылкой на `NULL`.

## <a name="contains"></a>содержащих

Выполняет поиск указанного блока в `network_link_registry` в этом `source_link_manager` объекте.

```cpp
bool contains(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на блок, который необходимо найти в объекте `source_link_manager`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если указанный блок найден; в противном случае — **значение false** .

## <a name="count"></a>расчета

Подсчитывает количество связанных блоков в объекте `source_link_manager`.

```cpp
size_t count();
```

### <a name="return-value"></a>Возвращаемое значение

Число связанных блоков в объекте `source_link_manager`.

## <a name="reference"></a>IsReference

Получает ссылку на объект `source_link_manager`.

```cpp
void reference();
```

## <a name="register_target_block"></a>register_target_block

Регистрирует целевой блок, содержащий этот объект `source_link_manager`.

```cpp
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Целевой блок, содержащий этот объект `source_link_manager`.

## <a name="release"></a>отпускании

Освобождает ссылку на объект `source_link_manager`.

```cpp
void release();
```

## <a name="remove"></a>отменит

Удаляет ссылку из объекта `source_link_manager`.

```cpp
bool remove(_EType _Link);
```

### <a name="parameters"></a>Параметры

*_Link*<br/>
Указатель на удаляемый блок, если он найден.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если ссылка была найдена и удалена; в противном случае — **значение false** .

## <a name="set_bound"></a>set_bound

Задает максимальное число ссылок на источники, которые могут быть добавлены к этому объекту `source_link_manager`.

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Параметры

*_MaxLinks*<br/>
Максимальное число ссылок.

## <a name="ctor"></a>source_link_manager

Формирует объект `source_link_manager`.

```cpp
source_link_manager();
```

## <a name="dtor"></a>~ source_link_manager

Уничтожает объект `source_link_manager`.

```cpp
~source_link_manager();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс single_link_registry](single-link-registry-class.md)<br/>
[Класс multi_link_registry](multi-link-registry-class.md)
