---
title: Класс CConnectionPoint
ms.date: 11/04/2016
f1_keywords:
- CConnectionPoint
- AFXDISP/CConnectionPoint
- AFXDISP/CConnectionPoint::CConnectionPoint
- AFXDISP/CConnectionPoint::GetConnections
- AFXDISP/CConnectionPoint::GetContainer
- AFXDISP/CConnectionPoint::GetIID
- AFXDISP/CConnectionPoint::GetMaxConnections
- AFXDISP/CConnectionPoint::GetNextConnection
- AFXDISP/CConnectionPoint::GetStartPosition
- AFXDISP/CConnectionPoint::OnAdvise
- AFXDISP/CConnectionPoint::QuerySinkInterface
helpviewer_keywords:
- CConnectionPoint [MFC], CConnectionPoint
- CConnectionPoint [MFC], GetConnections
- CConnectionPoint [MFC], GetContainer
- CConnectionPoint [MFC], GetIID
- CConnectionPoint [MFC], GetMaxConnections
- CConnectionPoint [MFC], GetNextConnection
- CConnectionPoint [MFC], GetStartPosition
- CConnectionPoint [MFC], OnAdvise
- CConnectionPoint [MFC], QuerySinkInterface
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
ms.openlocfilehash: ce72c156ab31b742a42d2960923fc56afff656c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369430"
---
# <a name="cconnectionpoint-class"></a>Класс CConnectionPoint

Определяет особый тип интерфейса, используемый для взаимодействия с другими объектами OLE и называемый "точкой подключения".

## <a name="syntax"></a>Синтаксис

```
class CConnectionPoint : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Формирует объект `CConnectionPoint`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CConnectionPoint::GetConnections](#getconnections)|Извлекает все точки соединения на карте соединения.|
|[CConnectionPoint::GetContainer](#getcontainer)|Извлекает контейнер элемента управления, которому принадлежит карта соединения.|
|[Точка подключения:GetIID](#getiid)|Извлекает идентификатор интерфейса точки соединения.|
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Извлекает максимальное количество точек соединения, поддерживаемых элементом управления.|
|[CConnectionPoint::GetNextConnection](#getnextconnection)|Извлекает указатель на элемент соединения в *pos*.|
|[CConnectionPoint::GetStartPosition](#getstartposition)|Начинаети итерацию карты, вернув значение POSITION, `GetNextConnection` которое может быть передано вызову.|
|[Точка подключения::Advise](#onadvise)|Вызывается по структуре при установлении или разрыве соединений.|
|[CConnectionPoint::КвиссинкИнтерфейс](#querysinkinterface)|Извлекает указатель на запрашиваемый интерфейс раковины.|

## <a name="remarks"></a>Remarks

В отличие от обычных интерфейсов OLE, которые используются для реализации и разоблачения функциональности управления OLE, точка соединения реализует исходящий интерфейс, способный инициировать действия на других объектах, таких как события стрельбы и уведомления об изменении.

Соединение состоит из двух частей: объекта, вызывающего интерфейс, называемого "источником", и объекта, реализующего интерфейс, который называется "потопить". Путем подвергать действию точку соединения, источник позволяет раковинам установить соединения к себе. Через механизм точки соединения исходный объект получает указатель на реализацию раковиной набора функций члена. Например, чтобы запустить событие, реализованное раковиной, источник может назвать подходящий метод реализации раковины.

По умолчанию `COleControl`класс a-derived реализует две точки соединения: одну для событий и одну для уведомлений об изменении свойства. Эти соединения используются, соответственно, для стрельбы событий и для уведомления раковины (например, контейнера управления) при изменении значения свойства. Поддержка также предоставляется для элементов управления OLE для реализации дополнительных точек соединения. Для каждой дополнительной точки соединения, реализованной в классе управления, необходимо объявить "часть соединения", которая реализует точку соединения. При реализации одной или нескольких точек соединения необходимо также объявить единую "карту соединения" в классе управления.

Следующий пример демонстрирует простую карту соединения и `Sample` одну точку соединения для управления OLE, состоящую из двух фрагментов кода: первая часть объявляет карту соединения и точку; вторая реализует эту карту и точку. Первый фрагмент вставляется в декларацию класса управления под **защищенным** разделом:

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

Макросы BEGIN_CONNECTION_PART и END_CONNECTION_PART объявляют встроенный класс `XSampleConnPt` (полученный из), `CConnectionPoint`который реализует эту конкретную точку соединения. Если вы хотите переопределить любые `CConnectionPoint` функции участника или добавить свои собственные функции, объявите их между этими двумя макросами. Например, CONNECTION_IID макрос `CConnectionPoint::GetIID` переопределяет функцию члена при размещении между этими двумя макросами.

Второй фрагмент кода вставляется в файл реализации (. CPP) вашего класса управления. Этот код реализует карту соединения, которая включает `SampleConnPt`в себя дополнительную точку соединения:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

После того, как эти фрагменты кода были вставлены, `ISampleSink` управление Sample OLE предоставляет точку соединения для интерфейса.

Как правило, точки соединения поддерживают "многокастинг", то есть возможность трансляции на несколько приемников, подключенных к тому же интерфейсу. Следующий фрагмент кода демонстрирует, как выполнить многокастинг, итерируя каждую раковину на точке соединения:

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

Этот пример извлекает текущий набор `SampleConnPt` соединений в `CConnectionPoint::GetConnections`точке соединения с вызовом. Затем он итерирует через `ISampleSink::SinkFunc` соединения и призывает к каждому активному соединению.

Для получения дополнительной `CConnectionPoint`информации об использовании, см. [Connection Points](../../mfc/connection-points.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="cconnectionpointcconnectionpoint"></a><a name="cconnectionpoint"></a>CConnectionPoint::CConnectionPoint

Формирует объект `CConnectionPoint`.

```
CConnectionPoint();
```

## <a name="cconnectionpointgetconnections"></a><a name="getconnections"></a>CConnectionPoint::GetConnections

Вызов ими функции для получения всех активных соединений для точки соединения.

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив активных соединений (поглотителей). Некоторые указатели в массиве могут быть NULL. Каждый указатель non-NULL в этом массиве можно безопасно преобразовать в указатель на интерфейс раковины с помощью литого оператора.

## <a name="cconnectionpointgetcontainer"></a><a name="getcontainer"></a>CConnectionPoint::GetContainer

Вызывается фреймворком для получения `IConnectionPointContainer` точки соединения.

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>Возвращаемое значение

В случае успеха указатель на контейнер; в противном случае NULL.

### <a name="remarks"></a>Remarks

Эта функция обычно реализуется макросом BEGIN_CONNECTION_PART.

## <a name="cconnectionpointgetiid"></a><a name="getiid"></a>Точка подключения:GetIID

Вызывается инфраструктурой для получения идентификатора интерфейса точки соединения.

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на идентификатор интерфейса точки соединения.

### <a name="remarks"></a>Remarks

Переопределить эту функцию, чтобы вернуть идентификатор интерфейса для этой точки соединения.

## <a name="cconnectionpointgetmaxconnections"></a><a name="getmaxconnections"></a>CConnectionPoint::GetMaxConnections

Вызывается инфраструктурой для получения максимального количества подключений, поддерживаемых точкой соединения.

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное количество соединений, поддерживаемых элементом управления, или -1, если нет предела.

### <a name="remarks"></a>Remarks

Реализация по умолчанию возвращается -1, не указывая на ограничение.

Переопределить эту функцию, если вы хотите ограничить количество раковин, которые могут подключиться к вашему управлению.

## <a name="cconnectionpointgetnextconnection"></a><a name="getnextconnection"></a>CConnectionPoint::GetNextConnection

Извлекает указатель на элемент соединения в *pos*.

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Упоняет ссылку на значение POSITION, возвращенное предыдущим `GetNextConnection` вызовом или [вызовом GetStartPosition.](#getstartposition)

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент соединения, указанный *pos,* или NULL.

### <a name="remarks"></a>Remarks

Эта функция наиболее полезна для итерации всех элементов на карте соединения. При итерации пропустить любые NULLs вернулся из этой функции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

## <a name="cconnectionpointgetstartposition"></a><a name="getstartposition"></a>CConnectionPoint::GetStartPosition

Начинаети итерацию карты, вернув значение POSITION, которое может быть передано вызову [GetNextConnection.](#getnextconnection)

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, указывающее исходное положение для итерации карты; или NULL, если карта пуста.

### <a name="remarks"></a>Remarks

Последовательность итерации не предсказуема; поэтому "первый элемент на карте" не имеет особого значения.

### <a name="example"></a>Пример

  Смотрите пример [CConnectionPoint::GetNextConnection](#getnextconnection).

## <a name="cconnectionpointonadvise"></a><a name="onadvise"></a>Точка подключения::Advise

Вызывается по системе, когда соединение устанавливается или нарушается.

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>Параметры

*bAdvise*<br/>
ПРАВДА, если соединение устанавливается; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Реализация по умолчанию не выполняет никаких действий.

Переизбь эту функцию, если требуется уведомление о подключении или отключении от точки соединения или отключении от нее.

## <a name="cconnectionpointquerysinkinterface"></a><a name="querysinkinterface"></a>CConnectionPoint::КвиссинкИнтерфейс

Извлекает указатель на запрашиваемый интерфейс раковины.

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>Параметры

*pUnkSink*<br/>
Идентификатор запрашиваемого интерфейса раковины.

*ppInterface*<br/>
Указатель на указатель интерфейса, идентифицированный *pUnkSink.* Если объект не поддерживает этот \* интерфейс, *ppInterface* настроен на NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также раздел

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
