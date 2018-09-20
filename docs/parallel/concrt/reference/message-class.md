---
title: Класс Message | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
dev_langs:
- C++
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5acca6c01b41b34c17aa5e7f949b9dab94362fa2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400956"
---
# <a name="message-class"></a>Класс message

Основной конверт сообщения, содержащий полезные данные, передаваемые между блоками обмена сообщениями.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных полезных данных в сообщении.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`type`|Псевдоним для `T`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[message](#ctor)|Перегружен. Создает объект `message`.|
|[~ сообщений деструктор](#dtor)|Уничтожает `message` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[add_ref](#add_ref)|Добавляет счетчик ссылок для `message` объекта. Используется для блоков сообщений, которые должны подсчет ссылок, чтобы определить время жизни сообщения.|
|[msg_id](#msg_id)|Возвращает идентификатор `message` объекта.|
|[remove_ref](#remove_ref)|Вычитает из счетчика ссылок для `message` объекта. Используется для блоков сообщений, которые должны подсчет ссылок, чтобы определить время жизни сообщения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[полезные данные](#payload)|Полезные данные `message` объекта.|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`message`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

##  <a name="add_ref"></a> add_ref

Добавляет счетчик ссылок для `message` объекта. Используется для блоков сообщений, которые должны подсчет ссылок, чтобы определить время жизни сообщения.

```
long add_ref();
```

### <a name="return-value"></a>Возвращаемое значение

Новое значение счетчика ссылок.

##  <a name="ctor"></a> Сообщение

Создает объект `message`.

```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```

### <a name="parameters"></a>Параметры

*_P*<br/>
Полезные данные сообщения.

*_Id*<br/>
Уникальный идентификатор этого сообщения.

*_Msg*<br/>
Ссылка или указатель на `message` объект.

### <a name="remarks"></a>Примечания

Конструктор, который принимает указатель на `message` как аргумент, создает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) исключения Если параметр `_Msg` является `NULL`.

##  <a name="dtor"></a> ~ сообщения

Уничтожает `message` объекта.

```
virtual ~message();
```

##  <a name="msg_id"></a> msg_id

Возвращает идентификатор `message` объекта.

```
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>Возвращаемое значение

`runtime_object_identity` Из `message` объекта.

##  <a name="payload"></a> полезные данные

Полезные данные `message` объекта.

```
T const payload;
```

##  <a name="remove_ref"></a> remove_ref

Вычитает из счетчика ссылок для `message` объекта. Используется для блоков сообщений, которые должны подсчет ссылок, чтобы определить время жизни сообщения.

```
long remove_ref();
```

### <a name="return-value"></a>Возвращаемое значение

Новое значение счетчика ссылок.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
