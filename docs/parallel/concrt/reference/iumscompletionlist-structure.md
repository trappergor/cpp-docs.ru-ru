---
title: Структура IUMSCompletionList
ms.date: 11/04/2016
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
ms.openlocfilehash: 567b8668934d81c49757660d1a60ca74eb033e68
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339512"
---
# <a name="iumscompletionlist-structure"></a>Структура IUMSCompletionList

Представляет список выполнения UMS. Когда поток UMS блокируется, отправляется назначенный планировщиком контекст планирования для принятия решения о том, что нужно запланировать для корня базового виртуального процессора, пока исходный поток заблокирован. Когда снимается блокировка исходного потока, операционная система ставит его в очередь списка выполнения, который доступен через этот интерфейс. Планировщик может запросить список выполнения в назначенном контексте планирования или в другом месте, в котором он выполняет поиск работы.

## <a name="syntax"></a>Синтаксис

```
struct IUMSCompletionList;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IUMSCompletionList::GetUnblockNotifications](#getunblocknotifications)|Получает цепочку `IUMSUnblockNotification` интерфейсов, представляющих контексты выполнения которого поток прокси разблокированы, с момента последнего выполнения этот метод был вызван.|

## <a name="remarks"></a>Примечания

Планировщик должен быть чрезвычайно осторожным, какие действия выполняются после использования этого интерфейса для извлечения из очереди элементов из списка завершения. Элементы должны размещаться на планировщика список работоспособным контекстам и сделать общедоступной, как можно скорее. Это вполне возможно, что один из элементов, исключенных получил владение произвольной блокировки. Планировщик не может выполнять произвольные вызовы функции, которые могут блокироваться между вызов для извлечения элементов из очереди и размещение этих элементов в список, который обычно возможен из планировщика.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IUMSCompletionList`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="getunblocknotifications"></a>  Метод IUMSCompletionList::GetUnblockNotifications

Получает цепочку `IUMSUnblockNotification` интерфейсов, представляющих контексты выполнения которого поток прокси разблокированы, с момента последнего выполнения этот метод был вызван.

```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Цепочка `IUMSUnblockNotification` интерфейсов.

### <a name="remarks"></a>Примечания

После перепланирования контекстов выполнения, возвращенные уведомления являются недопустимыми.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IUMSScheduler](iumsscheduler-structure.md)<br/>
[Структура IUMSUnblockNotification](iumsunblocknotification-structure.md)
