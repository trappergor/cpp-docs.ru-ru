---
title: Схемы подключения
ms.date: 11/04/2016
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
ms.openlocfilehash: 947cd09023ef4028a32db8e2e4e8b33f7e04e0dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374805"
---
# <a name="connection-maps"></a>Схемы подключения

Элементы управления OLE могут разоблачать интерфейсы для других приложений. Эти интерфейсы позволяют только доступ из контейнера в этот элемент управления. Если элемент управления OLE хочет получить доступ к внешним интерфейсам других объектов OLE, должна быть установлена точка соединения. Эта точка соединения позволяет элемент управления исходящих доступ к внешним картам диспетчеризации, таким как карты событий или функции уведомлений.

Библиотека класса Фонда Майкрософт предлагает модель программирования, поддерживающую точки соединения. В этой модели "карты соединения" используются для обозначения интерфейсов или точек соединения для управления OLE. Карты соединения содержат один макрос для каждой точки соединения. Для получения дополнительной [информации](../../mfc/reference/cconnectionpoint-class.md) о картах подключения см.

Как правило, элемент управления поддерживает только две точки соединения: одну для событий и одну для уведомлений об свойствах. Они реализуются `COleControl` базовым классом и не требуют дополнительной работы автором управления. Любые дополнительные точки подключения, которые вы хотите реализовать в своем классе, должны быть добавлены вручную. Для поддержки карт подключения и точек MFC предоставляет следующие макросы:

### <a name="connection-map-declaration-and-demarcation"></a>Декларация и демаркация карты подключения

|||
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Объявляет встроенный класс, который реализует дополнительную точку соединения (должна использоваться в декларации класса).|
|[END_CONNECTION_PART](#end_connection_part)|Завершает объявление точки соединения (должно быть использовано в классной декларации).|
|[CONNECTION_IID](#connection_iid)|Определяет идентификатор интерфейса точки соединения элемента управления.|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Объявляет, что карта соединения будет использоваться в классе (должна использоваться в декларации класса).|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|Начинается определение карты соединения (должно использоваться в реализации класса).|
|[END_CONNECTION_MAP](#end_connection_map)|Завершает определение карты соединения (должно использоваться в реализации класса).|
|[CONNECTION_PART](#connection_part)|Определяет точку соединения на карте соединения элемента управления.|

Следующие функции помогают раковине в создании и отключении соединения с помощью точек соединения:

### <a name="initializationtermination-of-connection-points"></a>Инициализация/прекращение точек соединения

|||
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|Устанавливает связь между источником и раковиной.|
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Разрывает связь между источником и раковиной.|

## <a name="begin_connection_part"></a><a name="begin_connection_part"></a>BEGIN_CONNECTION_PART

Используйте BEGIN_CONNECTION_PART макрос, чтобы начать определение дополнительных точек соединения за пределами событий и пунктов подключения уведомлений свойства.

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Укажите название класса управления, точка соединения которого это.

*локальныйКласс*<br/>
Укажите имя локального класса, реализуемого точкой соединения.

### <a name="remarks"></a>Remarks

В файле декларации (.h), определяющем функции участника для вашего класса, запустите точку соединения с BEGIN_CONNECTION_PART макросом, затем добавьте CONNECTION_IID макрос и любые другие функции члена, которые вы хотите реализовать, и заполните карту точки соединения с END_CONNECTION_PART макросом.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

## <a name="end_connection_part"></a><a name="end_connection_part"></a>END_CONNECTION_PART

Завершает объявление точки соединения.

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>Параметры

*локальныйКласс*<br/>
Укажите имя локального класса, реализуемого точкой соединения.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

## <a name="connection_iid"></a><a name="connection_iid"></a>CONNECTION_IID

Используйте между BEGIN_CONNECTION_PART и END_CONNECTION_PART макросов для определения идентификатора интерфейса для точки соединения, поддерживаемой вашим управлением OLE.

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
Идентификатор интерфейса интерфейса, вызванный точкой соединения.

### <a name="remarks"></a>Remarks

*Аргументом iid* является идентификатор интерфейса, используемый для определения интерфейса, который точка соединения вызовет на подключенные раковины. Пример:

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

определяет точку соединения, которая `ISinkInterface` вызывает интерфейс.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

## <a name="declare_connection_map"></a><a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP

Каждый `COleControl`класс, полученный в вашей программе, может предоставить карту соединения, чтобы указать дополнительные точки соединения, которые поддерживает элемент управления.

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>Remarks

Если элемент управления поддерживает дополнительные очки, используйте DECLARE_CONNECTION_MAP макрос в конце объявления класса. Затем в файле .cpp, определяющем функции элемента для класса, используйте BEGIN_CONNECTION_MAP макрос, CONNECTION_PART макросы для каждой из точек соединения элемента, а END_CONNECTION_MAP макроса для объявления конца карты соединения.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

## <a name="begin_connection_map"></a><a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP

Каждый `COleControl`класс, полученный в вашей программе, может предоставить карту соединения, чтобы указать точки соединения, которые будет поддерживать ваш элемент управления.

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Установить название класса управления, на карте соединения которого это.

*theBase*<br/>
Упогоняет название базового класса *Класса*.

### <a name="remarks"></a>Remarks

В реализации (. CPP) файл, который определяет функции участника для вашего класса, запустите карту соединения с BEGIN_CONNECTION_MAP макросом, а затем добавьте макрозаписи для каждой из точек соединения с помощью [CONNECTION_PART](#connection_part) макроса. Наконец, завершите карту соединения с [макросом END_CONNECTION_MAP.](#end_connection_map)

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

## <a name="end_connection_map"></a><a name="end_connection_map"></a>END_CONNECTION_MAP

Завершает определение карты соединения.

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

## <a name="connection_part"></a><a name="connection_part"></a>CONNECTION_PART

Отображает точку соединения для управления OLE к определенному идентификатору интерфейса.

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Укажите название класса управления, точка соединения которого это.

*Iid*<br/>
Идентификатор интерфейса интерфейса, вызванный точкой соединения.

*локальныйКласс*<br/>
Укажите имя локального класса, реализуемого точкой соединения.

### <a name="remarks"></a>Remarks

Пример:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

реализует карту соединения с точкой соединения, `IID_ISinkInterface` которая вызывает интерфейс.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

## <a name="afxconnectionadvise"></a><a name="afxconnectionadvise"></a>AfxConnectionAdvise

Назовите эту функцию, чтобы установить связь между источником, указанным *pUnkSrc*, и раковиной, указанной *pUnkSink*.

```
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD FAR* pdwCookie);
```

### <a name="parameters"></a>Параметры

*pUnkSrc*<br/>
Указатель на объект, который вызывает интерфейс.

*pUnkSink*<br/>
Указатель на объект, реализуемый интерфейсом.

*Iid*<br/>
Идентификатор интерфейса соединения.

*bRefCount*<br/>
TRUE указывает на то, что создание соединения должно привести к тому, что количество ссылок *pUnkSink* будет приравлено. FALSE указывает на то, что количество ссылок не должно быть приравнено.

*pdwCookie*<br/>
Указатель на DWORD, где возвращается идентификатор соединения. Это значение должно передаваться `AfxConnectionUnadvise` как параметр *dwCookie* при отключении соединения.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если соединение было установлено; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a>AfxConnectionUnadvise

Вызовите эту функцию, чтобы отключить соединение между источником, указанным *pUnkSrc*, и раковиной, указанной *pUnkSink.*

```
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD dwCookie);
```

### <a name="parameters"></a>Параметры

*pUnkSrc*<br/>
Указатель на объект, который вызывает интерфейс.

*pUnkSink*<br/>
Указатель на объект, реализуемый интерфейсом.

*Iid*<br/>
Идентификатор интерфейса интерфейса точки соединения.

*bRefCount*<br/>
TRUE указывает на то, что отключение соединения должно привести к тому, что число ссылок *pUnkSink* будет decremented. FALSE указывает на то, что количество ссылок не должно быть decremented.

*dwCookie*<br/>
Идентификатор `AfxConnectionAdvise`соединения, возвращенный .

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если соединение было отключено; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
