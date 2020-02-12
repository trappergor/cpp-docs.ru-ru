---
title: Структура IUMSUnblockNotification
ms.date: 11/04/2016
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
ms.openlocfilehash: d4fd95b1f11ed6edac26cb03e41e8b650acfafa3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139985"
---
# <a name="iumsunblocknotification-structure"></a>Структура IUMSUnblockNotification

Представляет уведомление диспетчера ресурсов о том, что прокси-поток, который заблокировал и запустил возврат к заданному контексту планирования планировщика, разблокирован и готов для планирования. Этот интерфейс является недопустимым, когда связанный с прокси-потоком контекст выполнения, возвращенный из метода `GetContext`, переносится.

## <a name="syntax"></a>Синтаксис

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Иумсунблоккнотификатион:: SPContext](#getcontext)|Возвращает интерфейс `IExecutionContext` для контекста выполнения, связанного с прокси-сервером потока, который был разблокирован. После того как этот метод возвращает управление, а базовый контекст выполнения был перепланирован с помощью вызова метода `IThreadProxy::SwitchTo`, этот интерфейс больше не является допустимым.|
|[Иумсунблоккнотификатион:: Жетнекстунблоккнотификатион](#getnextunblocknotification)|Возвращает следующий интерфейс `IUMSUnblockNotification` в цепочке, возвращенной из метода `IUMSCompletionList::GetUnblockNotifications`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IUMSUnblockNotification`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm. h

**Пространство имен:** concurrency

## <a name="getcontext"></a>Метод Иумсунблоккнотификатион:: oncontext

Возвращает интерфейс `IExecutionContext` для контекста выполнения, связанного с прокси-сервером потока, который был разблокирован. После того как этот метод возвращает управление, а базовый контекст выполнения был перепланирован с помощью вызова метода `IThreadProxy::SwitchTo`, этот интерфейс больше не является допустимым.

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IExecutionContext` для контекста выполнения для прокси-сервера потока, который был разблокирован.

## <a name="getnextunblocknotification"></a>Метод Иумсунблоккнотификатион:: Жетнекстунблоккнотификатион

Возвращает следующий интерфейс `IUMSUnblockNotification` в цепочке, возвращенной из метода `IUMSCompletionList::GetUnblockNotifications`.

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Следующий интерфейс `IUMSUnblockNotification` в цепочке, возвращаемой методом `IUMSCompletionList::GetUnblockNotifications`.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IUMSScheduler](iumsscheduler-structure.md)<br/>
[Структура IUMSCompletionList](iumscompletionlist-structure.md)
