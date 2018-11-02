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
ms.openlocfilehash: efa8a7bf9e14bd93682fcc2d5802a84f1bdb1e96
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629935"
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
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|Создает объект `CConnectionPoint`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CConnectionPoint::GetConnections](#getconnections)|Извлекает все точки подключения в сопоставлении подключения.|
|[CConnectionPoint::GetContainer](#getcontainer)|Возвращает контейнер элемента управления, которому принадлежит схеме подключения.|
|[CConnectionPoint::GetIID](#getiid)|Извлекает идентификатор интерфейса точки подключения.|
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|Возвращает максимальное число точек подключения, поддерживаемых элементом управления.|
|[CConnectionPoint::GetNextConnection](#getnextconnection)|Извлекает указатель на элемент подключения в *pos*.|
|[CConnectionPoint::GetStartPosition](#getstartposition)|Начинает итерацию карты, возвращая значение ПОЗИЦИИ, который может быть передан в `GetNextConnection` вызова.|
|[CConnectionPoint::OnAdvise](#onadvise)|Вызывается платформой при установлении или разрыва подключения.|
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|Извлекает указатель на интерфейс запрошенного приемника.|

## <a name="remarks"></a>Примечания

В отличие от обычных интерфейсов OLE, которые используются для реализации и предоставляют функциональные возможности элемента управления OLE, точки подключения реализует исходящего интерфейса, который может выполнять действия от других объектов, например для срабатывания событий и уведомлений об изменениях.

Подключение состоит из двух частей: объекте, вызывающем интерфейса, который называется «источник» и объект, реализующий интерфейс, называется «приемник». Предоставляя точку подключения, источник позволяет приемники для установки подключений к самому себе. Через механизм точек подключения исходный объект получает указатель на реализацию приемника набора функций-членов. Например срабатывание события, реализованного в приемник, источник можно вызвать соответствующий метод реализацию приемника.

По умолчанию `COleControl`-производный класс реализует две точки подключения: уведомления об изменении события и свойства. Эти соединения служат, соответственно, для обработки событий, а также для уведомления приемник (например, контейнер элемента управления), когда значение свойства было изменено. Поддержка также предоставляется для элементов управления OLE для реализации дополнительного соединения точек. Для каждой точки дополнительное подключение, реализованные в классе элемента управления необходимо объявить «часть подключения данных», которая реализует точку подключения. Если вы реализуете одну или несколько точек подключения, необходимо также объявить один «сопоставление подключения» в классе элемента управления.

В следующем примере показано простое соединение карты и одну точку подключения для `Sample` управления OLE, состоящий из двух фрагментов кода: первая часть объявляет сопоставление подключения и точки; второй реализует этой карты и точки. Первый фрагмент вставляется в объявление класса элемента управления, в разделе **защищенные** раздел:

[!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]

Макросы BEGIN_CONNECTION_PART и END_CONNECTION_PART объявить класс embedded `XSampleConnPt` (производный от `CConnectionPoint`), реализующий этой конкретной точке подключения. Если вы хотите переопределить любой `CConnectionPoint` функций-членов или добавить собственные функции-члены, можно объявить их между этими двумя макросами. Например, переопределения connection_iid-макрос `CConnectionPoint::GetIID` функция-член при помещении, между этими двумя макросами.

Второй фрагмент кода вставляется в файле реализации (. CPP) класса элемента управления. Этот код реализует карты подключения, которая содержит точку дополнительное подключение, `SampleConnPt`:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]

После вставки этих фрагментов кода примера OLE элемент управления предоставляет точку подключения для `ISampleSink` интерфейс.

Как правило точки подключения поддерживают «многоадресная рассылка», чего становится возможной для широковещательной передачи несколько приемников, подключенных к тот же интерфейс. В следующем фрагменте кода показано, как для выполнения многоадресной рассылки, перебирая каждый приемник в точке подключения:

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

В этом примере извлекает текущий набор подключений на `SampleConnPt` точки подключения с помощью вызова `CConnectionPoint::GetConnections`. Затем запрос проходит через подключения и вызовы `ISampleSink::SinkFunc` для каждого активного подключения.

Дополнительные сведения об использовании `CConnectionPoint`, см. в статье [точек подключения](../../mfc/connection-points.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CConnectionPoint`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="cconnectionpoint"></a>  CConnectionPoint::CConnectionPoint

Создает объект `CConnectionPoint`.

```
CConnectionPoint();
```

##  <a name="getconnections"></a>  CConnectionPoint::GetConnections

Вызывайте эту функцию для получения всех активных подключений для точки подключения.

```
const CPtrArray* GetConnections();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив активных соединениях (приемниках). Некоторые из указатели в массиве может иметь значение NULL. Каждого указатель отличное от NULL, в этом массиве можно безопасно преобразовать в указатель на интерфейс приемника, с помощью оператора приведения.

##  <a name="getcontainer"></a>  CConnectionPoint::GetContainer

Вызывается платформой для извлечения `IConnectionPointContainer` для точки подключения.

```
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения указатель в контейнер; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Эта функция обычно реализуют begin_connection_part-макрос.

##  <a name="getiid"></a>  CConnectionPoint::GetIID

Вызывается платформой для определения ИД интерфейса точки подключения.

```
virtual REFIID GetIID() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылку на идентификатор интерфейса точки подключения.

### <a name="remarks"></a>Примечания

Переопределите эту функцию для возврата идентификатора интерфейса для этой точки подключения.

##  <a name="getmaxconnections"></a>  CConnectionPoint::GetMaxConnections

Вызывается платформой для извлечения максимальное число подключений, поддерживаемого точкой подключения.

```
virtual int GetMaxConnections();
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число подключений, поддерживаемый элемент управления, или значение -1, если не ограничено.

### <a name="remarks"></a>Примечания

Реализация по умолчанию возвращает значение -1, указывающее, является отсутствие ограничений.

Переопределите эту функцию, если вы хотите ограничить число приемников, которые могут подключаться к вашему элементу управления.

##  <a name="getnextconnection"></a>  CConnectionPoint::GetNextConnection

Извлекает указатель на элемент подключения в *pos*.

```
LPUNKNOWN GetNextConnection(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Задает ссылку на значение ПОЗИЦИИ, возвращенное предыдущим `GetNextConnection` или [GetStartPosition](#getstartposition) вызова.

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент подключения, указанный *pos*, или значение NULL.

### <a name="remarks"></a>Примечания

Эта функция наиболее полезна для перебора всех элементов в сопоставление подключения. При итерации, пропустите все значения NULL, возвращаемых этой функцией.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]

##  <a name="getstartposition"></a>  CConnectionPoint::GetStartPosition

Начинает итерацию карты, возвращая значение ПОЗИЦИИ, который может быть передан в [GetNextConnection](#getnextconnection) вызова.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПОЗИЦИЯ значение, указывающее начальную позицию для выполнения итерации карты; или значение NULL, если сопоставление является пустым.

### <a name="remarks"></a>Примечания

В последовательности итерации не является прогнозируемым; Таким образом «первый элемент в сопоставлении» не имеет особой важности.

### <a name="example"></a>Пример

  См. в примере [CConnectionPoint::GetNextConnection](#getnextconnection).

##  <a name="onadvise"></a>  CConnectionPoint::OnAdvise

Вызывается платформой, когда подключение будет установлено или разорвано.

```
virtual void OnAdvise(BOOL bAdvise);
```

### <a name="parameters"></a>Параметры

*bAdvise*<br/>
Значение TRUE, если подключение установлено; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий.

Переопределите эту функцию, чтобы получать уведомления при приемники соединиться или отсоединиться от вашей точки подключения.

##  <a name="querysinkinterface"></a>  CConnectionPoint::QuerySinkInterface

Извлекает указатель на интерфейс запрошенного приемника.

```
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,
    void** ppInterface);
```

### <a name="parameters"></a>Параметры

*pUnkSink*<br/>
Идентификатор запрашиваемого интерфейса приемника.

*ppInterface*<br/>
Указатель на указатель интерфейса, идентифицируемый *pUnkSink*. Если объект не поддерживает этот интерфейс \* *ppInterface* имеет значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="see-also"></a>См. также

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

