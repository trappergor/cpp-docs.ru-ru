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
ms.openlocfilehash: bdf083e2ad418269e49e53dc164f2a60f693d5d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180223"
---
# <a name="iumsunblocknotification-structure"></a>Структура IUMSUnblockNotification

Представляет уведомление диспетчера ресурсов о том, что прокси-поток, который заблокировал и запустил возврат к заданному контексту планирования планировщика, разблокирован и готов для планирования. Этот интерфейс является недопустимым, когда связанный с прокси-потоком контекст выполнения, возвращенный из метода `GetContext`, переносится.

## <a name="syntax"></a>Синтаксис

```
struct IUMSUnblockNotification;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IUMSUnblockNotification::GetContext](#getcontext)|Возвращает `IExecutionContext` интерфейс для контекста выполнения, связанного с прокси-поток, который был разблокирован. Когда этот метод возвращает, базовый контекст выполнения будет повторно запущено через вызов `IThreadProxy::SwitchTo` метод, этот интерфейс больше не является допустимым.|
|[IUMSUnblockNotification::GetNextUnblockNotification](#getnextunblocknotification)|Возвращает следующий `IUMSUnblockNotification` интерфейс в цепочке, возвращенный методом `IUMSCompletionList::GetUnblockNotifications`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IUMSUnblockNotification`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="getcontext"></a>  Метод IUMSUnblockNotification::GetContext

Возвращает `IExecutionContext` интерфейс для контекста выполнения, связанного с прокси-поток, который был разблокирован. Когда этот метод возвращает, базовый контекст выполнения будет повторно запущено через вызов `IThreadProxy::SwitchTo` метод, этот интерфейс больше не является допустимым.

```
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

`IExecutionContext` Интерфейс для контекста выполнения для прокси-поток, который был разблокирован.

##  <a name="getnextunblocknotification"></a>  Метод IUMSUnblockNotification::GetNextUnblockNotification

Возвращает следующий `IUMSUnblockNotification` интерфейс в цепочке, возвращенный методом `IUMSCompletionList::GetUnblockNotifications`.

```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Следующий `IUMSUnblockNotification` интерфейс в цепочке, возвращенный методом `IUMSCompletionList::GetUnblockNotifications`.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IUMSScheduler](iumsscheduler-structure.md)<br/>
[Структура IUMSCompletionList](iumscompletionlist-structure.md)
