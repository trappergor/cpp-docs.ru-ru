---
title: Класс COleServerDoc
ms.date: 11/04/2016
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
helpviewer_keywords:
- COleServerDoc [MFC], COleServerDoc
- COleServerDoc [MFC], ActivateDocObject
- COleServerDoc [MFC], ActivateInPlace
- COleServerDoc [MFC], DeactivateAndUndo
- COleServerDoc [MFC], DiscardUndoState
- COleServerDoc [MFC], GetClientSite
- COleServerDoc [MFC], GetEmbeddedItem
- COleServerDoc [MFC], GetItemClipRect
- COleServerDoc [MFC], GetItemPosition
- COleServerDoc [MFC], GetZoomFactor
- COleServerDoc [MFC], IsDocObject
- COleServerDoc [MFC], IsEmbedded
- COleServerDoc [MFC], IsInPlaceActive
- COleServerDoc [MFC], NotifyChanged
- COleServerDoc [MFC], NotifyClosed
- COleServerDoc [MFC], NotifyRename
- COleServerDoc [MFC], NotifySaved
- COleServerDoc [MFC], OnDeactivate
- COleServerDoc [MFC], OnDeactivateUI
- COleServerDoc [MFC], OnDocWindowActivate
- COleServerDoc [MFC], OnResizeBorder
- COleServerDoc [MFC], OnShowControlBars
- COleServerDoc [MFC], OnUpdateDocument
- COleServerDoc [MFC], RequestPositionChange
- COleServerDoc [MFC], SaveEmbedding
- COleServerDoc [MFC], ScrollContainerBy
- COleServerDoc [MFC], UpdateAllItems
- COleServerDoc [MFC], CreateInPlaceFrame
- COleServerDoc [MFC], DestroyInPlaceFrame
- COleServerDoc [MFC], GetDocObjectServer
- COleServerDoc [MFC], OnClose
- COleServerDoc [MFC], OnExecOleCmd
- COleServerDoc [MFC], OnFrameWindowActivate
- COleServerDoc [MFC], OnGetEmbeddedItem
- COleServerDoc [MFC], OnReactivateAndUndo
- COleServerDoc [MFC], OnSetHostNames
- COleServerDoc [MFC], OnSetItemRects
- COleServerDoc [MFC], OnShowDocument
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
ms.openlocfilehash: 4cada70723c7fadc9c91c40380b8a7e9fc46a07a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58777263"
---
# <a name="coleserverdoc-class"></a>Класс COleServerDoc

Базовый класс для серверной документации OLE.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleServerDoc::COleServerDoc](#coleserverdoc)|Создает объект `COleServerDoc`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleServerDoc::ActivateDocObject](#activatedocobject)|Активирует связанный документ DocObject.|
|[COleServerDoc::ActivateInPlace](#activateinplace)|Активирует документ для редактирования на месте.|
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|Отключает пользовательский интерфейс сервера.|
|[COleServerDoc::DiscardUndoState](#discardundostate)|Удаляет сведения о состояния отмены.|
|[COleServerDoc::GetClientSite](#getclientsite)|Извлекает указатель на базовый `IOleClientSite` интерфейс.|
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|Возвращает указатель на элемент, представляющий весь документ.|
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|Возвращает текущий прямоугольник отсечения для редактирования на месте.|
|[COleServerDoc::GetItemPosition](#getitemposition)|Возвращает текущий прямоугольник позиции относительно клиентской области приложения-контейнера для редактирования на месте.|
|[COleServerDoc::GetZoomFactor](#getzoomfactor)|Возвращает значение масштаба в пикселях.|
|[COleServerDoc::IsDocObject](#isdocobject)|Определяет, является ли документ DocObject.|
|[COleServerDoc::IsEmbedded](#isembedded)|Указывает, является ли документ внедренный в документе-контейнере или запуска автономного.|
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|Возвращает значение TRUE, если элемент в настоящее время активации на месте.|
|[COleServerDoc::NotifyChanged](#notifychanged)|Уведомляет контейнеры о том, что пользователь изменил документа.|
|[COleServerDoc::NotifyClosed](#notifyclosed)|Уведомляет контейнеры о том, что пользователь закрыл его.|
|[COleServerDoc::NotifyRename](#notifyrename)|Уведомляет контейнеры о том, что пользователь переименован документа.|
|[COleServerDoc::NotifySaved](#notifysaved)|Уведомляет контейнеры о том, что пользователь сохранил документа.|
|[COleServerDoc::OnDeactivate](#ondeactivate)|Вызывается платформой, когда пользователь делает неактивным элемент, который был активирован на месте.|
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|Вызывается платформой для удаления элементов управления и другие элементы пользовательского интерфейса, созданные для активации на месте.|
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|Вызывается платформой при активации или отключении окна фрейма документа контейнера.|
|[COleServerDoc::OnResizeBorder](#onresizeborder)|Вызывается платформой при изменении размера окна документа или окна фрейма приложения-контейнера.|
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|Вызвано структурой для отображения или скрытия панели элементов управления для редактирования на месте.|
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|Вызывается платформой при сохранении документа сервера, который является внедренного элемента, обновление копии контейнера элемента.|
|[COleServerDoc::RequestPositionChange](#requestpositionchange)|Изменение положения фрейма редактирования на месте.|
|[COleServerDoc::SaveEmbedding](#saveembedding)|Сообщает приложение-контейнер для сохранения документа.|
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|Выполняет прокрутку документа-контейнера.|
|[COleServerDoc::UpdateAllItems](#updateallitems)|Уведомляет контейнеры о том, что пользователь изменил документа.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|Вызывается платформой для создания окна фрейма для редактирования на месте.|
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|Вызывается платформой для уничтожения окна фрейма для встроенного редактирования.|
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|Переопределите эту функцию для создания нового `CDocObjectServer` объекта и указывает, что этот документ является контейнером DocObject.|
|[COleServerDoc::OnClose](#onclose)|Вызывается платформой, когда контейнер запрашивает для закрытия документа.|
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|Выполняет указанную команду или отображает справку для команды.|
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|Вызывается платформой при активации или отключении окна фрейма контейнера.|
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|Вызывается для получения `COleServerItem` представляет весь документ; используется для получения внедренного элемента. Требуется реализация.|
|[COleServerDoc::OnReactivateAndUndo](#onreactivateandundo)|Вызывается платформой для отмены изменений, внесенных во время редактирования на месте.|
|[COleServerDoc::OnSetHostNames](#onsethostnames)|Вызывается платформой, когда контейнер устанавливает заголовок окна для внедренного объекта.|
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|Вызывается платформой для размещения окна фрейма редактирования на месте в пределах окна приложения-контейнера.|
|[COleServerDoc::OnShowDocument](#onshowdocument)|Вызвано структурой для отображения или скрытия документа.|

## <a name="remarks"></a>Примечания

Серверный документ может содержать [COleServerItem](../../mfc/reference/coleserveritem-class.md) объекты, которые представляют собой интерфейс сервера для внедренных или связанных элементов. При запуске серверного приложения в контейнере для редактирования внедренного элемента элемент загружается как свой собственный серверный документ; `COleServerDoc` объект содержит только один `COleServerItem` объект, состоящий из всего документа. При запуске серверного приложения в контейнере, чтобы изменить связанный элемент, существующий документ загружается с диска; часть содержимого документа будет выделен для обозначения связанного элемента.

`COleServerDoc` объекты также могут содержать элементы [COleClientItem](../../mfc/reference/coleclientitem-class.md) класса. Это позволяет вам создавать приложения на сервер контейнера. Платформа предоставляет функции для хранения правильно `COleClientItem` элементов во время обслуживания `COleServerItem` объектов.

Если серверное приложение не поддерживает ссылки, серверного документа всегда будет содержать только один элемент сервера, который представляет весь внедренный объект как документ. Если серверное приложение поддерживает ссылки, его необходимо создать серверный элемент каждый раз, когда выделение копируется в буфер обмена.

Чтобы использовать `COleServerDoc`, создать класс, производный от него и реализовать [OnGetEmbeddedItem](#ongetembeddeditem) функцией-членом, которая позволяет серверу для поддержки встроенных элементов. Наследуйте класс от `COleServerItem` реализации элементов в документах и возвращают объекты этого класса из `OnGetEmbeddedItem`.

Для поддержки связанных элементов `COleServerDoc` предоставляет [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem) функция-член. Можно использовать реализацию по умолчанию или переопределить его, если у вас есть собственный способ управления элементы документа.

Требуется один `COleServerDoc`-производный класс для каждого типа сервера документов поддерживает ваше приложение. Например, если серверное приложение поддерживает листы и диаграммы, необходимы два `COleServerDoc`-производные классы.

Дополнительные сведения о серверах см. в статье [серверов: Реализация сервера](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

`COleServerDoc`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="activatedocobject"></a>  COleServerDoc::ActivateDocObject

Активирует связанный документ DocObject.

```
void ActivateDocObject();
```

### <a name="remarks"></a>Примечания

По умолчанию `COleServerDoc` не поддерживает активные документы (называемый также DocObjects). Для включения такой поддержки, см. в разделе [GetDocObjectServer](#getdocobjectserver) и класс [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md).

##  <a name="activateinplace"></a>  COleServerDoc::ActivateInPlace

Активирует элемент для редактирования на месте.

```
BOOL ActivateInPlace();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; в противном случае 0, указывающий, что элемент полностью открыт.

### <a name="remarks"></a>Примечания

Эта функция выполняет все операции, необходимые для активации на месте. Он создает окно фрейма на месте, активируется и размером его к элементу, настраивает общий меню и другие элементы управления, прокручивает элемент в представлении и устанавливает фокус на окно фрейма на месте.

Эта функция вызывается реализация по умолчанию [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow). Эта функция вызывается в том случае, если приложение поддерживает другую команду для активации на месте (например, воспроизведение).

##  <a name="coleserverdoc"></a>  COleServerDoc::COleServerDoc

Создает `COleServerDoc` объекта без соединения с OLE системные библиотеки DLL.

```
COleServerDoc();
```

### <a name="remarks"></a>Примечания

Необходимо вызвать [COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) открыть связь с помощью OLE. Если вы используете [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) в приложении, `COleLinkingDoc::Register` вызывается для вас `COleLinkingDoc`в реализации `OnNewDocument`, `OnOpenDocument`, и `OnSaveDocument`.

##  <a name="createinplaceframe"></a>  COleServerDoc::CreateInPlaceFrame

Платформа вызывает эту функцию для создания окна фрейма для редактирования на месте.

```
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительское окно приложения-контейнера.

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно фрейма на месте, или значение NULL, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Реализация по умолчанию использует сведения, указанные в шаблоне документа для создания фрейма. Использовать это представление является первой представление, созданное для документа. В этом представлении временно отсоединения из исходного кадра и присоединения к только что созданный кадру.

Существует расширенная переопределяемый.

##  <a name="deactivateandundo"></a>  COleServerDoc::DeactivateAndUndo

Эта функция вызывается в том случае, если отменить поддерживаемых приложением, и пользователь нажимает отмены после активации элемента, но перед его редактирования.

```
BOOL DeactivateAndUndo();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Если приложение-контейнер написан с помощью библиотеки Microsoft Foundation Class, вызов этой функции приводит к [COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo) для вызова, который отключает пользовательский интерфейс сервера.

##  <a name="destroyinplaceframe"></a>  COleServerDoc::DestroyInPlaceFrame

Платформа вызывает эту функцию для уничтожения окна фрейма на месте и вернуть сервер в окне документа приложения в состояние до активации на месте.

```
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```

### <a name="parameters"></a>Параметры

*pFrameWnd*<br/>
Указатель на окно фрейма на месте будут уничтожены.

### <a name="remarks"></a>Примечания

Существует расширенная переопределяемый.

##  <a name="discardundostate"></a>  COleServerDoc::DiscardUndoState

Если пользователь выполняет операцию редактирования, которое нельзя отменить, эта функция заставить приложение-контейнер для отмены информацию о своем состоянии отмены.

```
BOOL DiscardUndoState();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Эта функция предоставляется таким образом, чтобы серверы, поддерживающие отмены можно освободить ресурсы, которые в противном случае будет использоваться сведения о состоянии отмены, который нельзя использовать.

##  <a name="getclientsite"></a>  COleServerDoc::GetClientSite

Извлекает указатель на базовый `IOleClientSite` интерфейс.

```
LPOLECLIENTSITE GetClientSite() const;
```

### <a name="return-value"></a>Возвращаемое значение

Извлекает указатель на базовый [IOleClientSite](/windows/desktop/api/oleidl/nn-oleidl-ioleclientsite) интерфейс.

##  <a name="getdocobjectserver"></a>  COleServerDoc::GetDocObjectServer

Переопределите эту функцию для создания нового `CDocObjectServer` элемента и возвращают указатель на него.

```
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```

### <a name="parameters"></a>Параметры

*pDocSite*<br/>
Указатель на `IOleDocumentSite` интерфейс, который будет подключаться этот документ на сервер.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CDocObjectServer`; Значение NULL, если произошел сбой операции.

### <a name="remarks"></a>Примечания

После активации сервер DocObject возвращение НЕНУЛЕВОЙ указатель показывает, что клиент может поддерживать DocObjects. Реализация по умолчанию возвращает значение NULL.

Типичная реализация для документа, который поддерживает DocObjects просто будут выделите новый `CDocObjectServer` объекта и вернуть его вызывающей стороне. Пример:

[!code-cpp[NVC_MFCOleServer#3](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]

##  <a name="getembeddeditem"></a>  COleServerDoc::GetEmbeddedItem

Вызывайте эту функцию, чтобы получить указатель на элемент, представляющий весь документ.

```
COleServerItem* GetEmbeddedItem();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент, представляющий весь документ; Значение NULL, если произошел сбой операции.

### <a name="remarks"></a>Примечания

Он вызывает [COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem), виртуальная функция без реализации по умолчанию.

##  <a name="getitemcliprect"></a>  COleServerDoc::GetItemClipRect

Вызовите `GetItemClipRect` функция-член для получения координат прямоугольника обрезки элемента, который редактируется на месте.

```
void GetItemClipRect(LPRECT lpClipRect) const;
```

### <a name="parameters"></a>Параметры

*lpClipRect*<br/>
Указатель на `RECT` структуры или `CRect` объект для получения координат прямоугольника обрезки элемента.

### <a name="remarks"></a>Примечания

Координаты указываются в пикселях относительно клиентской области окна приложения контейнера.

Рисование не будет выполняться за пределами прямоугольник отсечения. Как правило ограничиваются выполняется рисование. Эта функция позволяет определить, является ли пользователь прокрутил за пределы видимой области документа. Если Да, прокрутка документе-контейнере по мере необходимости посредством вызова [ScrollContainerBy](#scrollcontainerby).

##  <a name="getitemposition"></a>  COleServerDoc::GetItemPosition

Вызовите `GetItemPosition` функция-член для получения координат элемента выполняется редактирование на месте.

```
void GetItemPosition(LPRECT lpPosRect) const;
```

### <a name="parameters"></a>Параметры

*lpPosRect*<br/>
Указатель на `RECT` структуры или `CRect` объект для получения координат элемента.

### <a name="remarks"></a>Примечания

Координаты указываются в пикселях относительно клиентской области окна приложения контейнера.

Позиция элемента можно сравнить с текущим прямоугольником отсечения, чтобы определить степень, в которой элемент видим (или он не отображается) на экране.

##  <a name="getzoomfactor"></a>  COleServerDoc::GetZoomFactor

`GetZoomFactor` Функция-член определяет «масштаб» для элемента, который был активирован для редактирования на месте.

```
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,
    LPSIZE lpSizeDenom = NULL,
    LPCRECT lpPosRect = NULL) const;
```

### <a name="parameters"></a>Параметры

*lpSizeNum*<br/>
Указатель на объект класса `CSize` , будет содержать значения масштаба числитель. Может иметь значение NULL.

*lpSizeDenom*<br/>
Указатель на объект класса `CSize` , будет содержать знаменателя значения масштаба. Может иметь значение NULL.

*lpPosRect*<br/>
Указатель на объект класса `CRect` , описывающий новую позицию элемента. Если этот аргумент равен NULL, функция использует текущую позицию элемента.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент активируется для встроенного редактирования и его масштаба — отличного от 100% (1:1); в противном случае 0.

### <a name="remarks"></a>Примечания

Коэффициент масштабирования, в пикселях, — это доля размер элемента в его текущем степени. Если приложение-контейнер не задал степени элемента, его естественное экстент (что определяется [COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) используется.

Эта функция задает первые два аргумента для числителя и знаменателя из элемента «коэффициент масштабирования.» Если элемент не редактируется в месте, функция задает эти аргументы на значение по умолчанию 100% (или 1:1) и возвращает ноль. Для получения дополнительных сведений см. в разделе технических 40 примечание, [MFC/OLE в изменение размеров и масштабирования](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).

##  <a name="isdocobject"></a>  COleServerDoc::IsDocObject

Определяет, является ли документ DocObject.

```
BOOL IsDocObject() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если документ является DocObject; в противном случае — значение FALSE.

##  <a name="isembedded"></a>  COleServerDoc::IsEmbedded

Вызовите `IsEmbedded` функция-член для определения, представляет ли документ объекта, встроенного в контейнере.

```
BOOL IsEmbedded() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `COleServerDoc` объект — это документ, который представляет объект внедрены в контейнере; в противном случае — 0.

### <a name="remarks"></a>Примечания

Несмотря на то, что он может управляться как ссылка приложения-контейнера не внедрен документа, загруженного из файла. Документ, который внедряется в документе-контейнере считается для внедрения.

##  <a name="isinplaceactive"></a>  COleServerDoc::IsInPlaceActive

Вызовите `IsInPlaceActive` функция-член для определения, находится ли элемент в активном состоянии на месте.

```
BOOL IsInPlaceActive() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `COleServerDoc` объект активен на месте; в противном случае — 0.

##  <a name="notifychanged"></a>  COleServerDoc::NotifyChanged

Вызывайте эту функцию, чтобы уведомить всех связанных элементов, подключенных к документу, документ был изменен.

```
void NotifyChanged();
```

### <a name="remarks"></a>Примечания

Как правило эта функция вызывается, когда пользователь изменит некоторые глобальный атрибут, например размеры серверный документ. Если автоматическая ссылка в документ связан элемент OLE, элемент обновляется в соответствии с изменениями. В контейнере приложения, написанные с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.

> [!NOTE]
>  Эта функция включена для совместимости с OLE 1. Новые приложения должны использовать [UpdateAllItems](#updateallitems).

##  <a name="notifyclosed"></a>  COleServerDoc::NotifyClosed

Вызывайте эту функцию для уведомления контейнеры о том, что документ был закрыт.

```
void NotifyClosed();
```

### <a name="remarks"></a>Примечания

Когда пользователь выбирает команду "Закрыть" в меню "файл" `NotifyClosed` вызывается `COleServerDoc`в реализации [OnCloseDocument](../../mfc/reference/cdocument-class.md#onclosedocument) функция-член. В контейнере приложения, написанные с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.

##  <a name="notifyrename"></a>  COleServerDoc::NotifyRename

Вызывайте эту функцию после пользователь его переименовывает серверный документ.

```
void NotifyRename(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Параметры

*lpszNewName*<br/>
Указатель на строку, указав новое имя сервера документа. Обычно это полный URL-адрес.

### <a name="remarks"></a>Примечания

Когда пользователь выбирает команду «Сохранить как» из меню «Файл» `NotifyRename` вызывается `COleServerDoc`в реализации [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument) функция-член. Уведомляет систему OLE библиотеки DLL, которые в свою очередь уведомление контейнеров о этой функции. В контейнере приложения, написанные с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.

##  <a name="notifysaved"></a>  COleServerDoc::NotifySaved

Вызывайте эту функцию после пользователь сохраняет документ сервера.

```
void NotifySaved();
```

### <a name="remarks"></a>Примечания

При выборе команды "Сохранить" в меню "файл" `NotifySaved` вызывается для вас `COleServerDoc`в реализации [OnSaveDocument](../../mfc/reference/cdocument-class.md#onsavedocument). Уведомляет систему OLE библиотеки DLL, которые в свою очередь уведомление контейнеров о этой функции. В контейнере приложения, написанные с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.

##  <a name="onclose"></a>  COleServerDoc::OnClose

Вызывается платформой, когда контейнер запрашивает, что серверный документ закрыт.

```
virtual void OnClose(OLECLOSE dwCloseOption);
```

### <a name="parameters"></a>Параметры

*dwCloseOption*<br/>
Значение из перечисления OLECLOSE. Этот параметр может принимать одно из следующих значений:

- OLECLOSE_SAVEIFDIRTY файл сохраняется, если он был изменен.

- OLECLOSE_NOSAVE файл закрыт без сохранения.

- OLECLOSE_PROMPTSAVE, если файл был изменен, пользователю предлагается его сохранении.

### <a name="remarks"></a>Примечания

По умолчанию реализация вызывает `CDocument::OnCloseDocument`.

Дополнительные сведения и дополнительные значения, см. в разделе [OLECLOSE](/windows/desktop/api/oleidl/ne-oleidl-tagoleclose) в пакете Windows SDK.

##  <a name="ondeactivate"></a>  COleServerDoc::OnDeactivate

Вызывается платформой, когда пользователь делает неактивным внедренного или связанного элемента, который активен в данный момент на месте.

```
virtual void OnDeactivate();
```

### <a name="remarks"></a>Примечания

Эта функция восстанавливает в исходное состояние пользовательского интерфейса приложения-контейнера и уничтожает все меню и другие элементы управления, которые были созданы для активации на месте.

Сведения о состоянии отката должен освобождаться безусловно на этом этапе.

Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md)...

##  <a name="ondeactivateui"></a>  COleServerDoc::OnDeactivateUI

Вызывается, когда пользователь делает неактивным элемент, который был активирован на месте.

```
virtual void OnDeactivateUI(BOOL bUndoable);
```

### <a name="parameters"></a>Параметры

*bUndoable*<br/>
Указывает, можно ли отменить внесения изменений.

### <a name="remarks"></a>Примечания

Эта функция восстанавливает пользовательский интерфейс приложения-контейнера в исходное состояние, скрытия любого меню и другие элементы управления, которые были созданы для активации на месте.

Платформа всегда присваивает *bUndoable* значение false. Если сервер поддерживает отмены и выполняется операция, которую можно отменить, вызовите реализацию базового класса с *bUndoable* присвоено значение TRUE.

##  <a name="ondocwindowactivate"></a>  COleServerDoc::OnDocWindowActivate

Платформа вызывает эту функцию, чтобы активировать или деактивировать окно документа для редактирования на месте.

```
virtual void OnDocWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*bActivate*<br/>
Указывает, является ли окно документа перед активацией или деактивацией.

### <a name="remarks"></a>Примечания

Реализация по умолчанию, удаляет или добавляет элементы уровня кадров пользовательского интерфейса соответствующим образом. Переопределите эту функцию, если вы хотите выполнить дополнительные действия при активации или отключении документ, содержащий ваш элемент.

Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md)...

##  <a name="onexecolecmd"></a>  COleServerDoc::OnExecOleCmd

Платформа вызывает эту функцию для выполнения указанной команды или отобразить справку для команды.

```
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,
    DWORD nCmdID,
    DWORD nCmdExecOpt,
    VARIANTARG* pvarargIn,
    VARIANTARG* pvarargOut);
```

### <a name="parameters"></a>Параметры

*pguidCmdGroup*<br/>
Указатель на GUID, который определяет набор команд. Может иметь значение NULL для указания группы команд по умолчанию.

*nCmdID*<br/>
Команда для выполнения. Должна входить в группу, идентифицируемый *параметром pguidCmdGroup*.

*nCmdExecOut*<br/>
Способ объект должен выполняться команда, один или несколько из следующих значений из перечислений OLECMDEXECOPT перечисления:

OLECMDEXECOPT_DODEFAULT

OLECMDEXECOPT_PROMPTUSER

OLECMDEXECOPT_DONTPROMPTUSER

OLECMDEXECOPT_SHOWHELP

*pvarargIn*<br/>
Указатель на VARIANTARG, содержащую аргументы ввода для команды. Может иметь значение NULL.

*pvarargOut*<br/>
Указатель на VARIANTARG для получения выхода, возвращаемые значения из команды. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK, если выполнение прошло успешно; в противном случае — один из следующих кодов ошибки:

|Значение|Описание|
|-----------|-----------------|
|E_UNEXPECTED|Произошла непредвиденная ошибка|
|E_FAIL|Произошла ошибка|
|E_NOTIMPL|Указывает MFC сам должен попытаться перевести и отправлять команды|
|OLECMDERR_E_UNKNOWNGROUP|*параметром pguidCmdGroup* не равно NULL, но не указывает на известную группу команд|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* не является допустимой командой в группе *параметром pguidCmdGroup*|
|OLECMDERR_DISABLED|Команда, указанная *nCmdID* отключена и не может быть выполнена|
|OLECMDERR_NOHELP|Вызывающий объект и ответы для получения справки о команде, указанной *nCmdID* , но нет справочных сведений|
|OLECMDERR_CANCELED|Пользователь отменил выполнение|

### <a name="remarks"></a>Примечания

`COleCmdUI` можно использовать для включения, обновления и задать другие свойства DocObject команд пользовательского интерфейса. После инициализации команды, можно выполнить их при помощи `OnExecOleCmd`.

Платформа вызывает функцию, прежде чем переводить и отправлять команду документа OLE. Переопределите эту функцию для обработки стандартных команд документа OLE не требуется, но переопределение для этой функции необходимо указывать, если вам требуется возможность обрабатывать собственные команды обработки команд, которые принимают параметры, или возвращать результаты.

Большинство команд не принимают аргументы и возвращаемые значения. Для большинства команд вызывающий объект можно передать значения NULL *pvarargIn* и *pvarargOut*. Для команд, которые ожидают, что входные значения, вызывающий объект можно объявить и инициализировать переменную VARIANTARG и передать указатель на переменную в *pvarargIn*. Для команд, требующих одно значение аргумент можно хранить непосредственно в VARIANTARG и передан в функцию. Несколько аргументов, которые должны быть упакованы в VARIANTARG, с помощью одного из поддерживаемых типов (таких как `IDispatch` и SAFEARRAY).

Аналогичным образом, если команда возвращает аргументах, вызывающая сторона должна объявить VARIANTARG, инициализировать его значение VT_EMPTY и передает его адрес в *pvarargOut*. Если команда возвращает одно значение, объект можно сохранить это значение непосредственно в *pvarargOut*. Несколько выходных значений должны быть упакованы иным образом подходит для VARIANTARG.

Реализация базового класса этой функции будет стека OLE_COMMAND_MAP структур, связанный с целевой объект команды и повторите отправляемое команду, чтобы соответствующий обработчик. Реализация базового класса работает только с командами, которые не принимают аргументы и возвращаемые значения. Если вам нужно обрабатывать команды, которые принимают аргументы и не возвращают значения, необходимо переопределить эту функцию и работать с *pvarargIn* и *pvarargOut* параметры самостоятельно.

##  <a name="onframewindowactivate"></a>  COleServerDoc::OnFrameWindowActivate

Эта функция вызывается платформой при активации или отключении окна фрейма приложения-контейнера.

```
virtual void OnFrameWindowActivate(BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*bActivate*<br/>
Указывает, ли фрейм окна должен быть активируется или деактивируется.

### <a name="remarks"></a>Примечания

Реализация по умолчанию отменяет какие-либо режимы справки, возможно, окна фрейма. Переопределите эту функцию, если вы хотите выполнять специальную обработку при активации или отключении окна фрейма.

Дополнительные сведения см. в статье [активации](../../mfc/activation-cpp.md)...

##  <a name="ongetembeddeditem"></a>  COleServerDoc::OnGetEmbeddedItem

Вызывается платформой, когда приложение-контейнер вызывает серверное приложение для создания или редактирования внедренного элемента.

```
virtual COleServerItem* OnGetEmbeddedItem() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на элемент, представляющий весь документ; Значение NULL, если произошел сбой операции.

### <a name="remarks"></a>Примечания

Реализация по умолчанию отсутствует. Необходимо переопределить эту функцию, чтобы вернуть элемент, представляющий весь документ. Это возвращаемое значение должно быть объектом `COleServerItem`-производного класса.

##  <a name="onreactivateandundo"></a>  COleServerDoc::OnReactivateAndUndo

Платформа вызывает эту функцию, когда пользователь выбирает отмену изменений, внесенных в элемент, который активирована на месте, изменить и впоследствии деактивации.

```
virtual BOOL OnReactivateAndUndo();
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию ничего не делает за исключением того, возвращает значение FALSE, указывающее на ошибку.

Эту функцию можно переопределите, если приложение поддерживает отмены. Обычно необходимо выполнить операцию отмены, а затем активировать элемента путем вызова `ActivateInPlace`. Если приложение-контейнер записывается с помощью библиотеки Microsoft Foundation Class, при вызове метода `COleClientItem::ReactivateAndUndo` вызывает эту функцию для вызова.

##  <a name="onresizeborder"></a>  COleServerDoc::OnResizeBorder

Платформа вызывает эту функцию, изменении размера окна фрейма приложения-контейнера.

```
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,
    LPOLEINPLACEUIWINDOW lpUIWindow,
    BOOL bFrame);
```

### <a name="parameters"></a>Параметры

*lpRectBorder*<br/>
Указатель на `RECT` структуры или `CRect` , указывающий координаты границы.

*lpUIWindow*<br/>
Указатель на объект класса `IOleInPlaceUIWindow` , которому принадлежит текущий сеанс редактирования на месте.

*bFrame*<br/>
Значение TRUE, если *lpUIWindow* указывает на приложение-контейнер окна фрейма верхнего уровня или значение FALSE, если *lpUIWindow* указывает на окно рамки уровня документа для приложения-контейнера.

### <a name="remarks"></a>Примечания

Эта функция изменяет размер и настройка панелей инструментов и других элементов пользовательского интерфейса в соответствии с нового размера окна.

Дополнительные сведения см. в разделе [IOleInPlaceUIWindow](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceuiwindow) в пакете Windows SDK.

Существует расширенная переопределяемый.

##  <a name="onsethostnames"></a>  COleServerDoc::OnSetHostNames

Вызывается платформой, когда контейнер устанавливает или изменяет имена узлов для этого документа.

```
virtual void OnSetHostNames(
    LPCTSTR lpszHost,
    LPCTSTR lpszHostObj);
```

### <a name="parameters"></a>Параметры

*lpszHost*<br/>
Указатель на строку, которая указывает имя приложения-контейнера.

*lpszHostObj*<br/>
Указатель на строку, которая указывает имя контейнера для документа.

### <a name="remarks"></a>Примечания

Реализация по умолчанию изменяет заголовок документа для всех представлений, ссылающийся на этот документ.

Переопределите эту функцию, если приложение задает заголовки использованием другого механизма.

##  <a name="onsetitemrects"></a>  COleServerDoc::OnSetItemRects

Платформа вызывает эту функцию, чтобы изменить расположение окна фрейма редактирования на месте в окно приложения-контейнера.

```
virtual void OnSetItemRects(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Параметры

*lpPosRect*<br/>
Указатель на `RECT` структуры или `CRect` , указывающий положение окна фрейма на месте относительно клиентской области приложения-контейнера.

*lpClipRect*<br/>
Указатель на `RECT` структуры или `CRect` , определяющий прямоугольник отсечения окна фрейма на месте относительно клиентской области приложения-контейнера.

### <a name="remarks"></a>Примечания

Переопределите эту функцию, чтобы обновить коэффициент масштабирования представления, при необходимости.

Эта функция обычно вызывается в ответ на `RequestPositionChange` вызвать, несмотря на то, что может быть вызвана в любое время контейнера и запрос на изменение позиции элемента на месте.

##  <a name="onshowcontrolbars"></a>  COleServerDoc::OnShowControlBars

Платформа вызывает эту функцию для отображения или скрытия панели элементов управления серверного приложения, связанный с окном фрейма, идентифицируемый *pFrameWnd*.

```
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,
    BOOL bShow);
```

### <a name="parameters"></a>Параметры

*pFrameWnd*<br/>
Указатель на фрейм окна, панели элементов управления перед скрытием или отображением.

*bShow*<br/>
Определяет, являются ли панелей элементов управления, показано или скрыто.

### <a name="remarks"></a>Примечания

Реализация по умолчанию перечисляет все панели элементов управления, принадлежащие окну фрейма и скрывает или отображает их.

##  <a name="onshowdocument"></a>  COleServerDoc::OnShowDocument

Платформа вызывает `OnShowDocument` функционировать, когда серверный документ должен будет скрыто или показано.

```
virtual void OnShowDocument(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Указывает, будет ли пользовательский интерфейс к документу отображать и скрывать.

### <a name="remarks"></a>Примечания

Если *bShow* имеет значение TRUE, реализация по умолчанию активирует серверного приложения, при необходимости и вызывает приложение-контейнер для прокрутки его окна, чтобы элемент видим. Если *bShow* имеет значение FALSE, реализация по умолчанию деактивирует элемент посредством вызова `OnDeactivate`, а затем уничтожает или скрывает все окна фрейма, созданные для документа, кроме первого. Если остались документов не отображается, реализация по умолчанию скрывает серверное приложение.

##  <a name="onupdatedocument"></a>  COleServerDoc::OnUpdateDocument

Вызывается платформой при сохранении документа, внедренный элемент в составном документе.

```
virtual BOOL OnUpdateDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ был успешно обновлен; в противном случае 0.

### <a name="remarks"></a>Примечания

По умолчанию реализация вызывает [COleServerDoc::NotifySaved](#notifysaved) и [COleServerDoc::SaveEmbedding](#saveembedding) член функции, а затем помечает его как чистый. Переопределите эту функцию, если вы хотите выполнить специальная обработка при обновлении внедренного элемента.

##  <a name="requestpositionchange"></a>  COleServerDoc::RequestPositionChange

Вызов этой функции-члена для изменения положения элемента приложение-контейнер.

```
void RequestPositionChange(LPCRECT lpPosRect);
```

### <a name="parameters"></a>Параметры

*lpPosRect*<br/>
Указатель на `RECT` структуры или `CRect` объект, содержащий новое положение элемента.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается (в сочетании с `UpdateAllItems`) после изменения данных в элементе active на месте. После вызова этого метода, контейнер может или не может выполнить изменение путем вызова `OnSetItemRects`. Итоговая позиция может отличаться от того, запрошено.

##  <a name="saveembedding"></a>  COleServerDoc::SaveEmbedding

Вызывайте эту функцию, чтобы сообщить приложение-контейнер для сохранения внедренного объекта.

```
void SaveEmbedding();
```

### <a name="remarks"></a>Примечания

Эта функция вызывается автоматически из `OnUpdateDocument`. Обратите внимание, что эта функция приводит к обновляемого элемента на диске, поэтому обычно он вызывается только в результате конкретного действия пользователя.

##  <a name="scrollcontainerby"></a>  COleServerDoc::ScrollContainerBy

Вызовите `ScrollContainerBy` прокрутку документа-контейнера на значение, в пикселях, функция-член обозначается `sizeScroll`.

```
BOOL ScrollContainerBy(CSize sizeScroll);
```

### <a name="parameters"></a>Параметры

*sizeScroll*<br/>
Указывает, насколько далеко документе-контейнере для прокрутки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Положительные значения указывают, прокрутку вниз и вправо; отрицательные значения указывают, прокрутку вверх и влево.

##  <a name="updateallitems"></a>  COleServerDoc::UpdateAllItems

Вызывайте эту функцию, чтобы уведомить всех связанных элементов, подключенных к документу, документ был изменен.

```
void UpdateAllItems(
    COleServerItem* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL,
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Параметры

*pSender*<br/>
Указатель на элемент, измененный документ, или значение NULL, если все элементы должны быть обновлены.

*lHint*<br/>
Содержит сведения об изменении.

*pHint*<br/>
Указатель на объект хранения сведения об изменении.

*nDrawAspect*<br/>
Определяет, как элемент будет отображаться. Это значение из перечисления DVASPECT. Этот параметр может принимать одно из следующих значений:

- Элемент DVASPECT_CONTENT представлен таким образом, что он может отображаться в виде внедренного объекта внутри контейнера.

- DVASPECT_THUMBNAIL будет отображен в представлении «эскиз», чтобы она может отображаться в средствах просмотра.

- Элемент DVASPECT_ICON представлен значком.

- Элемент DVASPECT_DOCPRINT представляется так, как если бы печати с помощью команды "Печать" меню "файл".

### <a name="remarks"></a>Примечания

Как правило, эта функция вызывается, когда пользователь изменит серверный документ. Если автоматическая ссылка в документ связан элемент OLE, элемент обновляется в соответствии с изменениями. В контейнере приложения, написанные с использованием библиотеки классов Microsoft Foundation [OnChange](../../mfc/reference/coleclientitem-class.md#onchange) функцию-член `COleClientItem` вызывается.

Эта функция вызывает `OnUpdate` функция-член для каждого элемента документа, за исключением отправки элементов, передавая *pHint*, *lHint*, и *nDrawAspect*. Эти параметры можно используйте для передачи информации об изменениях, внесенных в документ элементы. Можно закодировать с помощью *lHint* или определить `CObject`-производный класс для хранения информации об изменениях и передайте объект этого класса, используя *pHint*. Переопределить `OnUpdate` функции-члена в вашей `COleServerItem`-производный класс для оптимизации обновления каждого элемента в зависимости от того, изменилось ли их представлением.

## <a name="see-also"></a>См. также

[Пример MFC HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDocument](../../mfc/reference/coledocument-class.md)<br/>
[Класс COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)<br/>
[Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
