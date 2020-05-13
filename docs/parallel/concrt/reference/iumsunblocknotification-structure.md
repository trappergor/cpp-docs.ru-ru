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
ms.openlocfilehash: 0b88ddd4184e982a5e07c536efc301eaa16f4a41
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368063"
---
# <a name="iumsunblocknotification-structure"></a>Структура IUMSUnblockNotification

Представляет уведомление диспетчера ресурсов о том, что прокси-поток, который заблокировал и запустил возврат к заданному контексту планирования планировщика, разблокирован и готов для планирования. Этот интерфейс является недопустимым, когда связанный с прокси-потоком контекст выполнения, возвращенный из метода `GetContext`, переносится.

## <a name="syntax"></a>Синтаксис

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[УВЕДОМИт о ней : Вопрос:](#getcontext)|Возвращает `IExecutionContext` интерфейс для контекста выполнения, связанного с разблокированным прокси потока. После того, как этот метод возвращается и основной `IThreadProxy::SwitchTo` контекст выполнения был перенесен через вызов к методу, этот интерфейс больше не действителен.|
|[УВЕДОМИтельно-изовещение О УМСУнблок::GetNextunblockNotification](#getnextunblocknotification)|Возвращает следующий `IUMSUnblockNotification` интерфейс в цепочке, возвращенный из метода. `IUMSCompletionList::GetUnblockNotifications`|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IUMSUnblockNotification`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="iumsunblocknotificationgetcontext-method"></a><a name="getcontext"></a>УВЕДОМЛЕНИЕ О НЕйизмом::Метод GetContext

Возвращает `IExecutionContext` интерфейс для контекста выполнения, связанного с разблокированным прокси потока. После того, как этот метод возвращается и основной `IThreadProxy::SwitchTo` контекст выполнения был перенесен через вызов к методу, этот интерфейс больше не действителен.

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IExecutionContext` для контекста выполнения к прокси-серверу потока, который разблокирован.

## <a name="iumsunblocknotificationgetnextunblocknotification-method"></a><a name="getnextunblocknotification"></a>УВЕДОМЛЕНИЕ О НЕй::Метод уведомления GetNextUnblockNotification

Возвращает следующий `IUMSUnblockNotification` интерфейс в цепочке, возвращенный из метода. `IUMSCompletionList::GetUnblockNotifications`

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Следующий `IUMSUnblockNotification` интерфейс в цепочке `IUMSCompletionList::GetUnblockNotifications`вернулся из метода.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IUMSScheduler](iumsscheduler-structure.md)<br/>
[Структура IUMSCompletionList](iumscompletionlist-structure.md)
