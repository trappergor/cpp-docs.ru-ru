---
title: Архетипа рабочей роли
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 7f28b9e64c88a5be440417dd9d22f129ee7d6edf
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495264"
---
# <a name="worker-archetype"></a>Архетипа рабочей роли

Классы, которые соответствуют *рабочей* архетипа, предоставляют код для обработки рабочих элементов, помещенных в очередь пула потоков.

**Реализация**

Чтобы реализовать класс, который соответствует этому архетипа, класс должен предоставить следующие возможности:

|Метод|Описание|
|------------|-----------------|
|[Initialize](#initialize)|Вызывается для инициализации рабочего объекта перед передачей [выполнения](#execute)любых запросов.|
|[Execute](#execute)|Вызывается для обработки рабочего элемента.|
|[Terminate](#terminate)|Вызывается для деинициализации рабочего объекта после того, как все запросы были переданы для [выполнения](#execute).|

|Typedef|Описание|
|-------------|-----------------|
|[RequestType](#requesttype)|Определение типа рабочего элемента, которое может быть обработано рабочим классом.|

Типичный *Рабочий* класс выглядит следующим образом:

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**Существующие реализации**

Эти классы соответствуют этому архетипа:

|Класс|Описание|
|-----------|-----------------|
|[кнонстателессворкер](../../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передает их в рабочий объект, который создается и уничтожается для каждого запроса.|

**Использует**

Эти параметры шаблона предполагают, что класс должен соответствовать этому архетипа:

|Имя параметра|Где используется|
|--------------------|-------------|
|*Работников*|[ксреадпул](../../atl/reference/cthreadpool-class.md)|
|*Работников*|[кнонстателессворкер](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil. h

## <a name="execute"></a>Воркерарчетипе:: Execute

Вызывается для обработки рабочего элемента.

```
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>Параметры

*получения*<br/>
Рабочий элемент для обработки. Рабочий элемент имеет тот же тип, что `RequestType`и.

*пвворкерпарам*<br/>
Пользовательский параметр, понятный рабочему классу. Также передается `Terminate`в `WorkerArchetype::Initialize` и.

*поверлаппед*<br/>
Указатель на структуру [OVERLAPPED](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) , используемую для создания очереди, в которой были поставлены рабочие элементы.

## <a name="initialize"></a>Воркерарчетипе:: Initialize

Вызывается для инициализации рабочего объекта перед передачей `WorkerArchetype::Execute`запросов.
```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>Параметры

*пвпарам*<br/>
Пользовательский параметр, понятный рабочему классу. Также передается `WorkerArchetype::Execute`в `WorkerArchetype::Terminate` и.

### <a name="return-value"></a>Возвращаемое значение

Возврат значения TRUE при успешном выполнении, FALSE при сбое.

## <a name="requesttype"></a>Воркерарчетипе:: RequestType

Определение типа рабочего элемента, которое может быть обработано рабочим классом.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>Примечания

Этот тип должен использоваться в качестве первого параметра `WorkerArchetype::Execute` и должен поддерживать приведение к ULONG_PTR и из него.

## <a name="terminate"></a>Воркерарчетипе:: Terminate

Вызывается для деинициализации рабочего объекта после передачи всех запросов в `WorkerArchetype::Execute`).

```
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>Параметры

*пвпарам*<br/>
Пользовательский параметр, понятный рабочему классу. Также передается `WorkerArchetype::Execute`в `WorkerArchetype::Initialize` и.

## <a name="see-also"></a>См. также

[Основные понятия](../../atl/active-template-library-atl-concepts.md)<br/>
[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
