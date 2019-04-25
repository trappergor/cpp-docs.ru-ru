---
title: Структура IUMSScheduler
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: f377d6079017266630434ce71602a7e70e58ae21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301868"
---
# <a name="iumsscheduler-structure"></a>Структура IUMSScheduler

Интерфейс абстракции планировщика, которому требуется, чтобы диспетчер ресурсов среды выполнения с параллелизмом передал ему потоки планировщика в пользовательском режиме (UMS). Диспетчер ресурсов среды выполнения с параллелизмом использует этот интерфейс для взаимодействия с планировщиками потоков UMS. Интерфейс `IUMSScheduler` наследует от интерфейса `IScheduler` .

## <a name="syntax"></a>Синтаксис

```
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|Назначает `IUMSCompletionList` интерфейс планировщика потоков UMS.|

## <a name="remarks"></a>Примечания

Если при реализации пользовательских планировщика, который взаимодействует с диспетчером ресурсов, и требуется, чтобы потоки UMS должна быть передана планировщику вместо обычных потоков Win32, необходимо предоставить реализацию `IUMSScheduler` интерфейс. Кроме того, следует задать значение политики для ключа политики планировщика `SchedulerKind` быть `UmsThreadDefault`. Если политика указывает потока UMS `IScheduler` интерфейс, который передается в качестве параметра [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) метод должен быть `IUMSScheduler` интерфейс.

Диспетчер ресурсов может передать потоки UMS только в операционных системах, поддерживающих UMS. 64-разрядных операционных системах с версией Windows 7 и более поздних версий поддерживают потоки UMS. При создании политики планировщика с `SchedulerKind` ключ, присваивается значение `UmsThreadDefault` и базовая платформа не поддерживает UMS, значение `SchedulerKind` ключ эту политику, будет изменен на значение `ThreadScheduler`. Следует всегда прочитать обратно этому значению политики перед ожиданием для получения потоков UMS.

`IUMSScheduler` Интерфейс — это один конец двустороннего канала связи между планировщиком и диспетчер ресурсов. Другой конец представленного `IResourceManager` и `ISchedulerProxy` интерфейсов, которые реализуются диспетчером ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[IScheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="setcompletionlist"></a>  Метод IUMSScheduler::SetCompletionList

Назначает `IUMSCompletionList` интерфейс планировщика потоков UMS.

```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>Параметры

*pCompletionList*<br/>
Интерфейс списка завершения для планировщика. Имеется один список для каждого планировщика.

### <a name="remarks"></a>Примечания

Диспетчер ресурсов будет вызывать этот метод на планировщика, который указывает, что ему нужны потоки UMS после планировщик запросил начального распределения ресурсов. Можно использовать планировщик `IUMSCompletionList` интерфейс, чтобы определить, когда разблокировать UMS прокси-поток. Он допустим только для доступа к этот интерфейс из прокси потоков, выполняющихся на корневом виртуальном процессоре, присвоенный планировщику UMS.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Структура IScheduler](ischeduler-structure.md)<br/>
[Структура IUMSCompletionList](iumscompletionlist-structure.md)<br/>
[Структура IResourceManager](iresourcemanager-structure.md)
