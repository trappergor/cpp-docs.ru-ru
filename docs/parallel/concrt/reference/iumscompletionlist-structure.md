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
ms.openlocfilehash: 02382ef4606a6e73804fcbd5ce7735ecf2f0dcc7
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140039"
---
# <a name="iumscompletionlist-structure"></a>Структура IUMSCompletionList

Представляет список выполнения UMS. Когда поток UMS блокируется, отправляется назначенный планировщиком контекст планирования для принятия решения о том, что нужно запланировать для корня базового виртуального процессора, пока исходный поток заблокирован. Когда снимается блокировка исходного потока, операционная система ставит его в очередь списка выполнения, который доступен через этот интерфейс. Планировщик может запросить список выполнения в назначенном контексте планирования или в другом месте, в котором он выполняет поиск работы.

## <a name="syntax"></a>Синтаксис

```cpp
struct IUMSCompletionList;
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Иумскомплетионлист:: Жетунблоккнотификатионс](#getunblocknotifications)|Извлекает цепочку интерфейсов `IUMSUnblockNotification`, представляющих контексты выполнения, связанные прокси-серверы потоков которых были разблокированы с момента последнего вызова этого метода.|

## <a name="remarks"></a>Remarks

Планировщик должен быть чрезвычайно осторожность, какие действия выполняются после использования этого интерфейса для вывода элементов из очереди в списке завершения. Элементы должны быть помещены в список готовых к выполнению контекстов планировщика и доступны как можно быстрее. Вполне возможно, что одному из выведенных из очереди элементов было предоставлено право владения произвольной блокировкой. Планировщик не может выполнять произвольные вызовы функций, которые могут блокировать между вызовом из очереди и размещением этих элементов в списке, доступ к которому можно получить в планировщике.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IUMSCompletionList`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm. h

**Пространство имен:** concurrency

## <a name="getunblocknotifications"></a>Метод Иумскомплетионлист:: Жетунблоккнотификатионс

Извлекает цепочку интерфейсов `IUMSUnblockNotification`, представляющих контексты выполнения, связанные прокси-серверы потоков которых были разблокированы с момента последнего вызова этого метода.

```cpp
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Цепочка интерфейсов `IUMSUnblockNotification`.

### <a name="remarks"></a>Remarks

Возвращенные уведомления недействительны после перепланирования контекстов выполнения.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IUMSScheduler](iumsscheduler-structure.md)<br/>
[Структура IUMSUnblockNotification](iumsunblocknotification-structure.md)
