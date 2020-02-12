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
ms.openlocfilehash: 45df744a9850510006e4bf887c8ed61b000a8e5c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139996"
---
# <a name="iumsscheduler-structure"></a>Структура IUMSScheduler

Интерфейс абстракции планировщика, которому требуется, чтобы диспетчер ресурсов среды выполнения с параллелизмом передал ему потоки планировщика в пользовательском режиме (UMS). Диспетчер ресурсов среды выполнения с параллелизмом использует этот интерфейс для взаимодействия с планировщиками потоков UMS. Интерфейс `IUMSScheduler` наследует от интерфейса `IScheduler` .

## <a name="syntax"></a>Синтаксис

```cpp
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Иумссчедулер:: Сеткомплетионлист](#setcompletionlist)|Назначает интерфейс `IUMSCompletionList` для планировщика потоков UMS.|

## <a name="remarks"></a>Remarks

При реализации пользовательского планировщика, который взаимодействует с диспетчер ресурсов и требуется передать потоки UMS планировщику вместо обычных потоков Win32, необходимо предоставить реализацию интерфейса `IUMSScheduler`. Кроме того, необходимо задать значение политики для ключа политики планировщика `SchedulerKind` `UmsThreadDefault`. Если политика указывает UMS-поток, интерфейс `IScheduler`, передаваемый в качестве параметра в метод [метод IResourceManager:: регистерсчедулер](iresourcemanager-structure.md#registerscheduler) , должен быть интерфейсом `IUMSScheduler`.

Диспетчер ресурсов может передать вам UMS-потоки только в операционных системах, имеющих функцию UMS. 64-разрядные операционные системы с версиями Windows 7 и более поздней версии поддерживают UMS-потоки. Если вы создаете политику планировщика с `SchedulerKind` ключом `UmsThreadDefault`, а базовая платформа не поддерживает UMS, значение ключа `SchedulerKind` в этой политике изменится на значение `ThreadScheduler`. Необходимо всегда считывать это значение политики, прежде чем ожидать получения потоков UMS.

Интерфейс `IUMSScheduler` — это один конец двустороннего канала связи между планировщиком и диспетчер ресурсов. Другой элемент представляется интерфейсами `IResourceManager` и `ISchedulerProxy`, которые реализуются диспетчер ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[IScheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm. h

**Пространство имен:** concurrency

## <a name="setcompletionlist"></a>Метод Иумссчедулер:: Сеткомплетионлист

Назначает интерфейс `IUMSCompletionList` для планировщика потоков UMS.

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>Параметры

*пкомплетионлист*<br/>
Интерфейс списка завершения для планировщика. Существует один список для каждого планировщика.

### <a name="remarks"></a>Remarks

Диспетчер ресурсов вызовет этот метод для планировщика, который указывает, что требуется UMS-потоки, после того как планировщик запрашивает начальное выделение ресурсов. Планировщик может использовать интерфейс `IUMSCompletionList`, чтобы определить, когда были разблокированы прокси-серверы потока UMS. Доступ к этому интерфейсу можно получить только из прокси-сервера потока, который работает на корневом виртуальном процессоре, назначенном планировщику UMS.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[полициелементкэй](concurrency-namespace-enums.md)<br/>
[Структура IScheduler](ischeduler-structure.md)<br/>
[Структура IUMSCompletionList](iumscompletionlist-structure.md)<br/>
[Структура IResourceManager](iresourcemanager-structure.md)
