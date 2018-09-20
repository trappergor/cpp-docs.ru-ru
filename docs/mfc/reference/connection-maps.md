---
title: Схемы подключения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1af235a597b70ac736ccd11de429d99e184d37b6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399643"
---
# <a name="connection-maps"></a>Схемы подключения

Элементы управления OLE получают возможность предоставлять интерфейсы другим приложениям. Эти интерфейсы только разрешить доступ из контейнера в этот элемент управления. Если для доступа к внешних интерфейсов других объектов OLE управления OLE, необходимо установить точку подключения. Этой точки подключения позволяет управления исходящий доступ к схемы внешней подготовки к отправке, таких как схемы событий или функции уведомления.

Библиотеки Microsoft Foundation Class предоставляет модель программирования, которая поддерживает точки подключения. В этой модели «подключения сопоставляет» используются для обозначения интерфейсы или точек подключения для элемента управления OLE. Схемы подключения содержат один макрос для каждой точки подключения. Дополнительные сведения о схемы подключения, см. в разделе [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) класса.

Как правило, элемент управления будет поддерживать только две точки подключения: один для событий и один для уведомлений свойство. Они реализованы с `COleControl` базового класса и требуют дополнительных действий разработчиком элемента управления. Всем точкам дополнительное подключение, необходимо реализовать в классе необходимо добавить вручную. Чтобы обеспечить поддержку схемы подключения и точки, MFC предоставляет следующие макросы:

### <a name="connection-map-declaration-and-demarcation"></a>Подключение карты объявление и определение границ

|||
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|Объявляет внедренный класс, который реализует точку дополнительное подключение (должен использоваться в объявлении класса).|
|[END_CONNECTION_PART](#end_connection_part)|Завершает объявление точки подключения (необходимо использовать в объявлении класса).|
|[CONNECTION_IID](#connection_iid)|Указывает идентификатор интерфейса точки подключения элемента управления.|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|Объявляет, что сопоставление подключения будет использоваться в классе (необходимо использовать в объявлении класса).|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|Начинается определение сопоставления подключения (необходимо использовать в реализации класса).|
|[END_CONNECTION_MAP](#end_connection_map)|Завершает определение сопоставления подключения (необходимо использовать в реализации класса).|
|[CONNECTION_PART](#connection_part)|Указывает точку подключения в сопоставление подключения элемента управления.|

Следующие функции помочь приемника в установке и разрыве подключения с помощью точки подключения.

### <a name="initializationtermination-of-connection-points"></a>Инициализации или остановки точек подключения

|||
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|Устанавливает соединение между источником и приемником.|
|[AfxConnectionUnadvise](#afxconnectionunadvise)|Разрывает соединение между источником и приемником.|

##  <a name="begin_connection_part"></a>  BEGIN_CONNECTION_PART

Используйте begin_connection_part-макрос, чтобы начать определение дополнительного соединения точек за точек подключения уведомлений события и свойства.

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Задает имя класса элемента управления, точка подключения которого это —.

*localClass*<br/>
Задает имя локального класса, реализующего точку подключения.

### <a name="remarks"></a>Примечания

В файле объявления (.h), который определяет функции-члены класса запуск точки подключения с begin_connection_part-макрос, а затем добавьте connection_iid-макрос и любые другие функции-члены для реализации и завершения соединения сопоставление точки с end_connection_part-макрос.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

##  <a name="end_connection_part"></a>  END_CONNECTION_PART

Завершает объявление точки подключения.

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>Параметры

*localClass*<br/>
Задает имя локального класса, реализующего точку подключения.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

##  <a name="connection_iid"></a>  CONNECTION_IID

Использовать между BEGIN_CONNECTION_PART и END_CONNECTION_PART макросы для определения идентификатор интерфейса для точки подключения, поддерживаемые элементом управления OLE.

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
Идентификатор интерфейса интерфейса, называется точкой подключения.

### <a name="remarks"></a>Примечания

*Iid* аргумент представляет собой интерфейс, идентификатор, используемый для определения интерфейса, который вызывает точки подключения на его подключенных приемников. Пример:

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

Указывает точку подключения, которая вызывает `ISinkInterface` интерфейс.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

##  <a name="declare_connection_map"></a>  DECLARE_CONNECTION_MAP

Каждый `COleControl`-производный класс в программе может предоставить сопоставление подключения для указания точки дополнительные подключения, которые поддерживает элемент управления.

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>Примечания

Если элемент управления поддерживает дополнительные точки, используйте declare_connection_map-макрос в конце объявления класса. Затем в CPP-файле, который определяет функции-члены класса, используйте begin_connection_map-макрос CONNECTION_PART макросы для каждой точки соединения элемента управления и end_connection_map-макрос для объявления конце сопоставления подключения.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

##  <a name="begin_connection_map"></a>  BEGIN_CONNECTION_MAP

Каждый `COleControl`-производный класс в программе может предоставить сопоставление подключения для указания точки подключения, которые будет поддерживать элемент управления.

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Указывает, что имя класса элемента управления, сопоставления которых подключение.

*theBase*<br/>
Указывает имя базового класса *theClass*.

### <a name="remarks"></a>Примечания

В реализации (. Файл CPP), определяющий член функции для класса, начните сопоставление подключения с begin_connection_map-макрос, а затем добавить макрос записи для каждого из вашей точки подключения с помощью [CONNECTION_PART](#connection_part) макрос. Наконец, выполните сопоставление подключения с [END_CONNECTION_MAP](#end_connection_map) макрос.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

##  <a name="end_connection_map"></a>  END_CONNECTION_MAP

Завершает определение карту подключения.

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

##  <a name="connection_part"></a>  CONNECTION_PART

Сопоставляет точку подключения для элемента управления OLE с идентификатором определенного интерфейса.

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Задает имя класса элемента управления, точка подключения которого это —.

*IID*<br/>
Идентификатор интерфейса интерфейса, называется точкой подключения.

*localClass*<br/>
Задает имя локального класса, реализующего точку подключения.

### <a name="remarks"></a>Примечания

Пример:

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

реализует карту соединения с точкой подключения, которая вызывает `IID_ISinkInterface` интерфейс.

### <a name="requirements"></a>Требования

  **Заголовок** afxdisp.h

##  <a name="afxconnectionadvise"></a>  AfxConnectionAdvise

Вызывайте эту функцию для установления соединения между исходным, определяемое *pUnkSrc*и в качестве приемника, определяемое *pUnkSink*.

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
Указатель на объект, реализующий интерфейс.

*IID*<br/>
Идентификатор интерфейса подключения.

*bRefCount*<br/>
Значение TRUE указывает, что создается подключение приводит количество ссылок на *pUnkSink* увеличивается. Значение FALSE указывает, что счетчик ссылок не будет увеличено.

*pdwCookie*<br/>
Указатель на значение типа DWORD, где возвращается идентификатор подключения. Это значение должно быть передано как *dwCookie* параметра `AfxConnectionUnadvise` при отключении подключения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если установлено подключение; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

##  <a name="afxconnectionunadvise"></a>  AfxConnectionUnadvise

Вызывайте эту функцию, чтобы разорвать подключение между исходным, определяемое *pUnkSrc*и в качестве приемника, определяемое *pUnkSink*.

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
Указатель на объект, реализующий интерфейс.

*IID*<br/>
Идентификатор интерфейса интерфейса точки подключения.

*bRefCount*<br/>
Значение TRUE указывает, что разрыв соединения приводит количество ссылок на *pUnkSink* уменьшается. Значение FALSE указывает, что счетчик ссылок не должен быть уменьшается на единицу.

*dwCookie*<br/>
Идентификатор соединения, возвращенный `AfxConnectionAdvise`.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если соединение был отключен; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
