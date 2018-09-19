---
title: Рабочий Архетип | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80bd9984afa3ce1fc6cda4e0b48cfa59e7e84b56
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118457"
---
# <a name="worker-archetype"></a>Рабочий Архетип

Классы, которые соответствуют *рабочих* архетипа предоставить код для обработки рабочих элементов в очередь в пуле потоков.

**Реализация**

Реализация класса, удовлетворяющие этот архетипа, класс должен предоставлять следующие возможности:

|Метод|Описание|
|------------|-----------------|
|[Initialize](#initialize)|Вызывается для инициализации объекта рабочей роли, прежде чем все запросы передаются [Execute](#execute).|
|[Execute](#execute)|Вызывается для обработки рабочего элемента.|
|[Terminate](#terminate)|Для отмены инициализации рабочий объект после все запросы были переданы вызванной [Execute](#execute).|

|Typedef|Описание|
|-------------|-----------------|
|[RequestType](#requesttype)|Typedef для типа рабочего элемента, который может быть обработан с помощью класса рабочих.|

Типичный *рабочих* класс выглядит следующим образом:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Существующие реализации**

Эти классы соответствуют этой архетипа:

|Класс|Описание|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передают их в рабочий объект, который создается и уничтожается при каждом запросе.|

**Используйте**

Эти параметры шаблона класса в соответствии с этой архетипа следующие преимущества.

|Имя параметра|Где используется|
|--------------------|-------------|
|*Рабочей роли*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*Рабочей роли*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

## <a name="execute"></a>WorkerArchetype::Execute

Вызывается для обработки рабочего элемента.

```
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Параметры

*Запрос*<br/>
Рабочий элемент должен быть обработан. Рабочий элемент имеет тот же тип, что `RequestType`.

*pvWorkerParam*<br/>
Пользовательский параметр, воспринимаемый рабочий класс. Также передается `WorkerArchetype::Initialize` и `Terminate`.

*pOverlapped*<br/>
Указатель на [OVERLAPPED](/windows/desktop/api/minwinbase/ns-minwinbase-_overlapped) структура, используемая для создания очереди, на какие рабочие элементы были поставлены в очередь.

## <a name="initialize"></a> WorkerArchetype::Initialize

Вызывается для инициализации объекта рабочей роли, прежде чем все запросы передаются `WorkerArchetype::Execute`.
```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Параметры

*pvParam*<br/>
Пользовательский параметр, воспринимаемый рабочий класс. Также передается `WorkerArchetype::Terminate` и `WorkerArchetype::Execute`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

## <a name="requesttype"></a> WorkerArchetype::RequestType

Typedef для типа рабочего элемента, который может быть обработан с помощью класса рабочих.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Примечания

Этот тип должен использоваться в качестве первого параметра `WorkerArchetype::Execute` и должен быть способен приводимого и из ULONG_PTR.

## <a name="terminate"></a> WorkerArchetype::Terminate

Для отмены инициализации рабочий объект после все запросы были переданы вызванной `WorkerArchetype::Execute`).

```
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Параметры

*pvParam*<br/>
Пользовательский параметр, воспринимаемый рабочий класс. Также передается `WorkerArchetype::Initialize` и `WorkerArchetype::Execute`.

## <a name="see-also"></a>См. также

[Основные понятия](../../atl/active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)

