---
title: Класс COleServerItem
ms.date: 11/04/2016
f1_keywords:
- COleServerItem
- AFXOLE/COleServerItem
- AFXOLE/COleServerItem::COleServerItem
- AFXOLE/COleServerItem::AddOtherClipboardData
- AFXOLE/COleServerItem::CopyToClipboard
- AFXOLE/COleServerItem::DoDragDrop
- AFXOLE/COleServerItem::GetClipboardData
- AFXOLE/COleServerItem::GetDocument
- AFXOLE/COleServerItem::GetEmbedSourceData
- AFXOLE/COleServerItem::GetItemName
- AFXOLE/COleServerItem::GetLinkSourceData
- AFXOLE/COleServerItem::GetObjectDescriptorData
- AFXOLE/COleServerItem::IsConnected
- AFXOLE/COleServerItem::IsLinkedItem
- AFXOLE/COleServerItem::NotifyChanged
- AFXOLE/COleServerItem::OnDoVerb
- AFXOLE/COleServerItem::OnDraw
- AFXOLE/COleServerItem::OnDrawEx
- AFXOLE/COleServerItem::OnGetClipboardData
- AFXOLE/COleServerItem::OnGetExtent
- AFXOLE/COleServerItem::OnInitFromData
- AFXOLE/COleServerItem::OnQueryUpdateItems
- AFXOLE/COleServerItem::OnRenderData
- AFXOLE/COleServerItem::OnRenderFileData
- AFXOLE/COleServerItem::OnRenderGlobalData
- AFXOLE/COleServerItem::OnSetColorScheme
- AFXOLE/COleServerItem::OnSetData
- AFXOLE/COleServerItem::OnSetExtent
- AFXOLE/COleServerItem::OnUpdate
- AFXOLE/COleServerItem::OnUpdateItems
- AFXOLE/COleServerItem::SetItemName
- AFXOLE/COleServerItem::GetDataSource
- AFXOLE/COleServerItem::OnHide
- AFXOLE/COleServerItem::OnOpen
- AFXOLE/COleServerItem::OnShow
- AFXOLE/COleServerItem::m_sizeExtent
helpviewer_keywords:
- COleServerItem [MFC], COleServerItem
- COleServerItem [MFC], AddOtherClipboardData
- COleServerItem [MFC], CopyToClipboard
- COleServerItem [MFC], DoDragDrop
- COleServerItem [MFC], GetClipboardData
- COleServerItem [MFC], GetDocument
- COleServerItem [MFC], GetEmbedSourceData
- COleServerItem [MFC], GetItemName
- COleServerItem [MFC], GetLinkSourceData
- COleServerItem [MFC], GetObjectDescriptorData
- COleServerItem [MFC], IsConnected
- COleServerItem [MFC], IsLinkedItem
- COleServerItem [MFC], NotifyChanged
- COleServerItem [MFC], OnDoVerb
- COleServerItem [MFC], OnDraw
- COleServerItem [MFC], OnDrawEx
- COleServerItem [MFC], OnGetClipboardData
- COleServerItem [MFC], OnGetExtent
- COleServerItem [MFC], OnInitFromData
- COleServerItem [MFC], OnQueryUpdateItems
- COleServerItem [MFC], OnRenderData
- COleServerItem [MFC], OnRenderFileData
- COleServerItem [MFC], OnRenderGlobalData
- COleServerItem [MFC], OnSetColorScheme
- COleServerItem [MFC], OnSetData
- COleServerItem [MFC], OnSetExtent
- COleServerItem [MFC], OnUpdate
- COleServerItem [MFC], OnUpdateItems
- COleServerItem [MFC], SetItemName
- COleServerItem [MFC], GetDataSource
- COleServerItem [MFC], OnHide
- COleServerItem [MFC], OnOpen
- COleServerItem [MFC], OnShow
- COleServerItem [MFC], m_sizeExtent
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
ms.openlocfilehash: e0d48d37d8262c4e82a8532333bbd12f193087b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604138"
---
# <a name="coleserveritem-class"></a>Класс COleServerItem

Предоставляет серверный интерфейс элементам OLE.

## <a name="syntax"></a>Синтаксис

```
class COleServerItem : public CDocItem
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleServerItem::COleServerItem](#coleserveritem)|Создает объект `COleServerItem`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|Помещает форматов представления и преобразования в `COleDataSource` объекта.|
|[COleServerItem::CopyToClipboard](#copytoclipboard)|Копирование элемента в буфер обмена.|
|[COleServerItem::DoDragDrop](#dodragdrop)|Выполняет операцию перетаскивания и вставки.|
|[COleServerItem::GetClipboardData](#getclipboarddata)|Возвращает источник данных для использования в передачи данных (Перетаскивание или буфер обмена).|
|[COleServerItem::GetDocument](#getdocument)|Возвращает серверный документ, который содержит элемент.|
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|Возвращает данные CF_EMBEDSOURCE для объекта OLE.|
|[COleServerItem::GetItemName](#getitemname)|Возвращает имя элемента. Используется только для связанных элементов.|
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|Возвращает данные CF_LINKSOURCE для объекта OLE.|
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|Возвращает данные CF_OBJECTDESCRIPTOR для объекта OLE.|
|[COleServerItem::IsConnected](#isconnected)|Указывает, присоединен ли в данный момент элемента в контейнер active.|
|[COleServerItem::IsLinkedItem](#islinkeditem)|Указывает, представляет ли элемент связанного объекта OLE.|
|[COleServerItem::NotifyChanged](#notifychanged)|Обновляет все контейнеры с обновлением автоматическую ссылку.|
|[COleServerItem::OnDoVerb](#ondoverb)|Вызывается для выполнения команды.|
|[COleServerItem::OnDraw](#ondraw)|Вызывается, когда контейнер запрашивает для рисования элемента; требуется реализация.|
|[COleServerItem::OnDrawEx](#ondrawex)|Вызывается для специализированных элементов рисования.|
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|Вызывается платформой для получения данных, будут скопированы в буфер обмена.|
|[COleServerItem::OnGetExtent](#ongetextent)|Вызывается платформой для определения размера объекта OLE.|
|[COleServerItem::OnInitFromData](#oninitfromdata)|Вызывается платформой для инициализации объекта OLE, используя содержимое указанного объекта передачи данных.|
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|Вызывается, чтобы определить, требуется ли обновление связанных элементов.|
|[COleServerItem::OnRenderData](#onrenderdata)|Извлекает данные как часть отложенной подготовки к просмотру.|
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|Извлекает данные в `CFile` объект как часть отложенной подготовки к просмотру.|
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|Извлекает данные в HGLOBAL как часть отложенной подготовки к просмотру.|
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|Вызывается для задания элемента цветовую схему.|
|[COleServerItem::OnSetData](#onsetdata)|Вызывается для задания элемента данных.|
|[COleServerItem::OnSetExtent](#onsetextent)|Вызывается платформой для установки размера объекта OLE.|
|[COleServerItem::OnUpdate](#onupdate)|Вызывается при некоторую часть документа элемент принадлежит к изменяется.|
|[COleServerItem::OnUpdateItems](#onupdateitems)|Вызывается для обновления кэша представления всех элементов на серверном документе.|
|[COleServerItem::SetItemName](#setitemname)|Задает имя элемента. Используется только для связанных элементов.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[COleServerItem::GetDataSource](#getdatasource)|Возвращает объект, используемый для хранения преобразования форматов.|
|[COleServerItem::OnHide](#onhide)|Вызвано структурой для скрытия элемента OLE.|
|[COleServerItem::OnOpen](#onopen)|Вызывается платформой для отображения объекта OLE в отдельном окне верхнего уровня.|
|[COleServerItem::OnShow](#onshow)|Вызывается, когда контейнер запрашивает, чтобы отобразить элемент.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleServerItem::m_sizeExtent](#m_sizeextent)|Сообщает серверу о какая часть элемента OLE является видимым.|

## <a name="remarks"></a>Примечания

Связанный элемент может представлять некоторые или все из серверного документа. Внедренный элемент всегда представляет документ всего сервера.

`COleServerItem` Класс определяет несколько функций является переопределяемым элементом, вызываемые OLE системных библиотек динамической компоновки (DLL), обычно в ответ на запросы из приложения-контейнера. Эти функции-члены разрешить приложение-контейнер для манипуляции элементом, косвенно различными способами, например, путем его отображения, выполняется его команд или извлекает свои данные в различных форматах.

Чтобы использовать `COleServerItem`, создать класс, производный от него и реализовать [OnDraw](#ondraw) и [Serialize](../../mfc/reference/cobject-class.md#serialize) функций-членов. `OnDraw` Функция предоставляет представление элемента, позволяя, чтобы он отображался в открывшемся составной документ приложения-контейнера в метафайл. `Serialize` Функции `CObject` предоставляет собственное представление элемента, благодаря чему embedded могут передаваться между приложениями, сервера и контейнера. [OnGetExtent](#ongetextent) предоставляет размеру элемента в контейнер, включение контейнера для определения размера элемента.

Дополнительные сведения о серверах и щелкните ссылку, см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md) и «Создание контейнера и сервера приложений» в статье [контейнеры: Дополнительные функции](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

`COleServerItem`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="addotherclipboarddata"></a>  COleServerItem::AddOtherClipboardData

Вызывайте эту функцию для размещения форматы представления и преобразования для элемента OLE в указанном `COleDataSource` объекта.

```
void AddOtherClipboardData(COleDataSource* pDataSource);
```

### <a name="parameters"></a>Параметры

*pDataSource*<br/>
Указатель на `COleDataSource` объекта, в котором должны размещаться данные.

### <a name="remarks"></a>Примечания

Вы должны реализованы [OnDraw](#ondraw) функция-член для задания формата представления (рисунок метафайл) для элемента. Для поддержки других форматов преобразования, зарегистрируйте их с помощью [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, возвращаемый [GetDataSource](#getdatasource) и переопределить [OnRenderData](#onrenderdata) функция-член предоставляют данные в форматы, которые требуется поддерживать.

##  <a name="coleserveritem"></a>  COleServerItem::COleServerItem

Создает `COleServerItem` и добавляет его в коллекцию элементов документа в серверном документе.

```
COleServerItem(
    COleServerDoc* pServerDoc,
    BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*pServerDoc*<br/>
Указатель на документ, который будет содержать новый элемент.

*bAutoDelete*<br/>
Флаг, указывающий, может ли быть удален объект при отпускании ссылку на него. Задайте значение FALSE, если `COleServerItem` объект является неотъемлемой частью данных документа, который необходимо удалить. Задайте значение TRUE, если объект является структурой вторичной, используемый для определения диапазона в данных документа, которые могут удаляться платформой.

##  <a name="copytoclipboard"></a>  COleServerItem::CopyToClipboard

Вызывайте эту функцию, чтобы скопировать элемента OLE в буфер обмена.

```
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>Параметры

*bIncludeLink*<br/>
Задайте значение TRUE, если необходимо скопировать данные на ссылку в буфер обмена. Задайте значение FALSE, если сервер приложений не поддерживает ссылки.

### <a name="remarks"></a>Примечания

Эта функция использует [OnGetClipboardData](#ongetclipboarddata) функция-член для создания [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, содержащий данные элемента OLE в форматы, поддерживаемые. Функция затем помещает `COleDataSource` объектов из буфера обмена с помощью [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard) функции. `COleDataSource` Объект включает собственных данных элемента и его представление в формате CF_METAFILEPICT, а также данные в форматах любое преобразование, выберите для поддержки. Вы должны реализованы [Serialize](../../mfc/reference/cobject-class.md#serialize) и [OnDraw](#ondraw) для работы этой функции-члена.

##  <a name="dodragdrop"></a>  COleServerItem::DoDragDrop

Вызовите `DoDragDrop` функция-член для выполнения операции перетаскивания и вставки.

```
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,
    CPoint ptOffset,
    BOOL bIncludeLink = FALSE,
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,
    LPCRECT lpRectStartDrag = NULL);
```

### <a name="parameters"></a>Параметры

*lpRectItem*<br/>
Прямоугольник элемента на экране, в пикселях, относительно клиентской области.

*ptOffset*<br/>
Смещение от *lpItemRect* место положение указателя мыши во время операции перетаскивания.

*bIncludeLink*<br/>
Задайте значение TRUE, если необходимо скопировать данные на ссылку в буфер обмена. Ему присвоено значение FALSE, если приложение не поддерживает ссылки.

*dwEffects*<br/>
Определяет эффекты, которые источник перетаскивания будет разрешать в операции перетаскивания (сочетание копирования, перемещения и ссылка).

*lpRectStartDrag*<br/>
Указатель на прямоугольник, который определяет, где фактически начинается перетаскивание. Дополнительные сведения см. в разделе "Примечания".

### <a name="return-value"></a>Возвращаемое значение

Значение из перечисления DROPEFFECT. Если это DROPEFFECT_MOVE, исходные данные должны удаляться.

### <a name="remarks"></a>Примечания

Операции перетаскивания и вставки не начинается немедленно. Он ждет, пока указатель мыши покидает прямоугольник, определяемый *lpRectStartDrag* или пока не прошли указанного числа миллисекунд. Если *lpRectStartDrag* имеет значение NULL, прямоугольник по умолчанию используется, чтобы перетаскивания запускается, когда указатель мыши перемещается на один пиксель.

Время задержки задается параметр раздела реестра. Время задержки можно изменить, вызвав [CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Если вы не укажете время задержки, используется значение по умолчанию 200 миллисекунд. Время задержки перетащите хранится следующим образом:

- Перетащите Windows NT задержка времени хранится в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay.

- Время задержки перетащите 3.x Windows хранится в WIN. INI-файл, в разделе "[Windows}".

- Перетащите Windows 95/98 задержка времени хранится в кэшированной версии WIN. INI.

Для перетащите Дополнительные сведения о том, как задержки сведения хранятся в реестре или. INI-файл, см. в разделе [WriteProfileString](/windows/desktop/api/winbase/nf-winbase-writeprofilestringa) в пакете Windows SDK.

##  <a name="getclipboarddata"></a>  COleServerItem::GetClipboardData

Вызывайте эту функцию для заполнения указанного [COleDataSource](../../mfc/reference/coledatasource-class.md) объект со всеми данными, которые будут скопированы в буфер обмена при вызове вы [CopyToClipboard](#copytoclipboard) (также будет переноситься те же данные, если вы вызывается [DoDragDrop](#dodragdrop)).

```
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>Параметры

*pDataSource*<br/>
Указатель на `COleDataSource` объект, который будет получать данные элемента OLE в любых форматах, поддерживаемых.

*bIncludeLink*<br/>
Значение TRUE, если необходимо скопировать данные на ссылку в буфер обмена. Значение FALSE, если серверное приложение не поддерживает ссылки.

*lpOffset*<br/>
Смещение в пикселях от начала координат объекта курсора мыши.

*lpSize*<br/>
Размер объекта в пикселях.

### <a name="remarks"></a>Примечания

Эта функция вызывает [GetEmbedSourceData](#getembedsourcedata) функцию-член для получения собственных данных для объекта OLE и вызовы [AddOtherClipboardData](#addotherclipboarddata) функция-член для получения формат представления и все Поддерживаемые форматы преобразования. Если *bIncludeLink* имеет значение TRUE, функция также вызывает [GetLinkSourceData](#getlinksourcedata) для получения данных ссылки для элемента.

Переопределите эту функцию, если вы хотите поместить в форматах `COleDataSource` объекта до или после этих форматах, предоставляемые `CopyToClipboard`.

##  <a name="getdatasource"></a>  COleServerItem::GetDataSource

Вызовите эту функцию для получения [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, используемый для хранения форматов преобразования, поддерживаемые приложением для сервера.

```
COleDataSource* GetDataSource();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `COleDataSource` объект, используемый для хранения форматов преобразования.

### <a name="remarks"></a>Примечания

Если требуется, чтобы серверное приложение предоставлять данные в различные форматы во время передачи данных operations, зарегистрировать их с `COleDataSource` объект, возвращаемый этой функцией. Например, если вы хотите указать CF_TEXT представление элемента OLE для буфера обмена или операции перетаскивания и вставки, зарегистрировать формат с `COleDataSource` эта функция возвращает объект и Переопределите `OnRenderXxxData` функция-член предоставить данные.

##  <a name="getdocument"></a>  COleServerItem::GetDocument

Вызывайте эту функцию, чтобы получить указатель на документ, который содержит элемент.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, который содержит элемент; Значение NULL, если элемент не является частью документа.

### <a name="remarks"></a>Примечания

Это позволяет доступ к документу сервера, который передается в качестве аргумента для `COleServerItem` конструктор.

##  <a name="getembedsourcedata"></a>  COleServerItem::GetEmbedSourceData

Вызывайте эту функцию для получения данных CF_EMBEDSOURCE для объекта OLE.

```
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*lpStgMedium*<br/>
Указатель на [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) структуру, которая будет получать данные CF_EMBEDSOURCE для объекта OLE.

### <a name="remarks"></a>Примечания

Этот формат включает собственных данных элемента. Вы должны реализованы `Serialize` функция-член для правильной работы этой функции.

Результат может затем добавить к источнику данных с помощью [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически [COleServerItem::OnGetClipboardData](#ongetclipboarddata).

Дополнительные сведения см. в разделе [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) в пакете Windows SDK.

##  <a name="getitemname"></a>  COleServerItem::GetItemName

Вызывайте эту функцию для получения имени элемента.

```
const CString& GetItemName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя элемента.

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается только для связанных элементов.

##  <a name="getlinksourcedata"></a>  COleServerItem::GetLinkSourceData

Вызывайте эту функцию для получения данных CF_LINKSOURCE для объекта OLE.

```
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*lpStgMedium*<br/>
Указатель на [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) структуру, которая будет получать данные CF_LINKSOURCE для объекта OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Этот формат включает идентификатор CLSID, описывающий тип объекта OLE и сведения, необходимые для поиска документа, содержащего объекта OLE.

Результат затем можно добавить к источнику данных с помощью [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически [OnGetClipboardData](#ongetclipboarddata).

Дополнительные сведения см. в разделе [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) в пакете Windows SDK.

##  <a name="getobjectdescriptordata"></a>  COleServerItem::GetObjectDescriptorData

Вызывайте эту функцию для получения данных CF_OBJECTDESCRIPTOR для объекта OLE.

```
void GetObjectDescriptorData(
    LPPOINT lpOffset,
    LPSIZE lpSize,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*lpOffset*<br/>
Смещение щелчка мыши от верхнего левого угла объекта OLE. Может иметь значение NULL.

*lpSize*<br/>
Размер объекта OLE. Может иметь значение NULL.

*lpStgMedium*<br/>
Указатель на [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) структуру, которая будет получать данные CF_OBJECTDESCRIPTOR для объекта OLE.

### <a name="remarks"></a>Примечания

Данные копируются в `STGMEDIUM` структуры, на которые указывают *lpStgMedium*. Этот формат включает сведения, необходимые для Специальная вставка диалогового окна.

Дополнительные сведения см. в разделе [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) в пакете Windows SDK.

##  <a name="isconnected"></a>  COleServerItem::IsConnected

Вызывайте эту функцию, чтобы увидеть, подключено ли объекта OLE.

```
BOOL IsConnected() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент подключен; в противном случае 0.

### <a name="remarks"></a>Примечания

Объект OLE считается подключен, если один или несколько контейнеров содержит ссылки на элемент. Элемент подключен в том случае, если счетчик ссылок на него больше 0 или если это внедренного элемента.

##  <a name="islinkeditem"></a>  COleServerItem::IsLinkedItem

Вызывайте эту функцию, находится ли элемент OLE связанный элемент.

```
BOOL IsLinkedItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент является связанный элемент; в противном случае 0.

### <a name="remarks"></a>Примечания

Если элемент является допустимым и не возвращается в список документов, внедренных элементов связанного элемента. Связанный элемент может или не подключен к контейнеру.

Это часто используется тот же класс для связанных и внедренных элементов. `IsLinkedItem` позволяет сделать связанных элементов, которые ведут себя иначе, чем внедренных элементов, хотя обычно используется многократно код.

##  <a name="m_sizeextent"></a>  COleServerItem::m_sizeExtent

Этот элемент указывает, что сервер сколько объекта отображается в документе-контейнере.

```
CSize m_sizeExtent;
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию [OnSetExtent](#onsetextent) задает этот член.

##  <a name="notifychanged"></a>  COleServerItem::NotifyChanged

Эта функция вызывается после изменения связанного элемента.

```
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Параметры

*nDrawAspect*<br/>
Изменилось значение из перечисления DVASPECT, которое указывает, какие элементы объекта OLE. Этот параметр может иметь любой из следующих значений:

- Элемент DVASPECT_CONTENT представлен таким образом, что он может отображаться в виде внедренного объекта внутри контейнера.

- DVASPECT_THUMBNAIL будет отображен в представлении «эскиз», чтобы она может отображаться в средствах просмотра.

- Элемент DVASPECT_ICON представлен значком.

- Элемент DVASPECT_DOCPRINT представляется так, как если бы печати с помощью команды "Печать" меню "файл".

### <a name="remarks"></a>Примечания

Если элемент-контейнер связан документ автоматического ссылка, элемент обновляется в соответствии с изменениями. В контейнере приложений, использующих библиотеку MFC [COleClientItem::OnChange](../../mfc/reference/coleclientitem-class.md#onchange) вызывается в ответ.

##  <a name="ondoverb"></a>  COleServerItem::OnDoVerb

Вызывается платформой для выполнения указанной команды.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Указывает команду для выполнения. Он может принимать любое из следующих:

|Значение|Значение|Символ|
|-----------|-------------|------------|
|0|первичный глагол|OLEIVERB_PRIMARY|
|1|Вторичный команды|(Нет)|
|- 1|Отображаемым элементом для редактирования|OLEIVERB_SHOW|
|- 2|Изменение элемента в отдельном окне|OLEIVERB_OPEN|
|- 3|Скрытие элементов|OLEIVERB_HIDE|

Значение-1, обычно является псевдонимом для другой команды. Если открыть изменения не поддерживается, -2 имеет тот же эффект, что значение -1. Дополнительные значения, см. в разделе [функция IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Если приложение-контейнер был записан с помощью библиотеки Microsoft Foundation Class, эта функция вызывается, когда [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate) функция-член соответствующего `COleClientItem` вызова объекта. По умолчанию реализация вызывает [OnShow](#onshow) функция-член, если указан первичный глагол или OLEIVERB_SHOW, [OnOpen](#onopen) Если указан дополнительный глагол или OLEIVERB_OPEN, и [OnHide ](#onhide) указываемое OLEIVERB_HIDE. По умолчанию реализация вызывает `OnShow` Если *iVerb* не является одной из команд, перечисленных выше.

Переопределите эту функцию, если ваш первичный глагол не содержит элемент. Например если элемент является звукозаписи, его первичный глагол — Play не пришлось бы отображать серверное приложение для воспроизведения элемента.

Дополнительные сведения см. в разделе [функция IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) в пакете Windows SDK.

##  <a name="ondraw"></a>  COleServerItem::OnDraw

Вызывается платформой для отрисовки элемента OLE в метафайл.

```
virtual BOOL OnDraw(
    CDC* pDC,
    CSize& rSize) = 0;
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на [CDC](../../mfc/reference/cdc-class.md) объект, для которого для рисования элемента. Контекста отображения автоматически подключается для контекста отображения, атрибут, можно вызывать функции атрибут, несмотря на то, что это сделает метафайла конкретного устройства.

*rSize*<br/>
Размер в единицах HIMETRIC, в которой следует нарисовать метафайла.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент успешно рисования; в противном случае 0.

### <a name="remarks"></a>Примечания

Представлением элемента OLE в метафайл используется для отображения элемента в приложении-контейнере. Если приложение-контейнер был записан с помощью библиотеки Microsoft Foundation Class, метафайла используется [рисования](../../mfc/reference/coleclientitem-class.md#draw) функция-член соответствующего [COleClientItem](../../mfc/reference/coleclientitem-class.md) объекта. Реализация по умолчанию отсутствует. Необходимо переопределить эту функцию для рисования элемента в указанный контекст устройства.

##  <a name="ondrawex"></a>  COleServerItem::OnDrawEx

Вызывается платформой для всех рисования.

```
virtual BOOL OnDrawEx(
    CDC* pDC,
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на [CDC](../../mfc/reference/cdc-class.md) объект, для которого для рисования элемента. Контроллер домена автоматически подключается к атрибутов контроллера домена, можно вызывать функции атрибут, несмотря на то, что это сделает метафайла конкретного устройства.

*nDrawAspect*<br/>
Значение из перечисления DVASPECT. Этот параметр может иметь любой из следующих значений:

- Элемент DVASPECT_CONTENT представлен таким образом, что он может отображаться в виде внедренного объекта внутри контейнера.

- DVASPECT_THUMBNAIL будет отображен в представлении «эскиз», чтобы она может отображаться в средствах просмотра.

- Элемент DVASPECT_ICON представлен значком.

- Элемент DVASPECT_DOCPRINT представляется так, как если бы печати с помощью команды "Печать" меню "файл".

*rSize*<br/>
Размер элемента в единицах HIMETRIC.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент успешно рисования; в противном случае 0.

### <a name="remarks"></a>Примечания

По умолчанию реализация вызывает `OnDraw` при DVASPECT равен DVASPECT_CONTENT; в противном случае происходит сбой.

Переопределите эту функцию для обеспечения аспекты, отличные от DVASPECT_CONTENT, например DVASPECT_ICON или DVASPECT_THUMBNAIL представления данных.

##  <a name="ongetclipboarddata"></a>  COleServerItem::OnGetClipboardData

Вызывается платформой для получения `COleDataSource` объект, содержащий все данные, которые будут размещаться в буфер обмена с помощью вызова [CopyToClipboard](#copytoclipboard) функция-член.

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>Параметры

*bIncludeLink*<br/>
Задайте значение TRUE, если необходимо скопировать данные на ссылку в буфер обмена. Задайте значение FALSE, если сервер приложений не поддерживает ссылки.

*lpOffset*<br/>
Смещение курсора мыши от начала координат объекта в пикселях.

*lpSize*<br/>
Размер объекта в пикселях.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [COleDataSource](../../mfc/reference/coledatasource-class.md) объект, содержащий данные из буфера обмена.

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция вызывает [GetClipboardData](#getclipboarddata).

##  <a name="ongetextent"></a>  COleServerItem::OnGetExtent

Вызывается платформой для извлечения размер в единицах HIMETRIC объекта OLE.

```
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Параметры

*nDrawAspect*<br/>
Указывает пропорции объекта OLE, границы которого должны быть получены. Этот параметр может иметь любой из следующих значений:

- Элемент DVASPECT_CONTENT представлен таким образом, что он может отображаться в виде внедренного объекта внутри контейнера.

- DVASPECT_THUMBNAIL будет отображен в представлении «эскиз», чтобы она может отображаться в средствах просмотра.

- Элемент DVASPECT_ICON представлен значком.

- Элемент DVASPECT_DOCPRINT представляется так, как если бы печати с помощью команды "Печать" меню "файл".

*rSize*<br/>
Ссылка на `CSize` объект, который будет принимать размер объекта OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Если приложение-контейнер был записан с помощью библиотеки Microsoft Foundation Class, эта функция вызывается, когда [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) функция-член соответствующего `COleClientItem` вызова объекта. Реализация по умолчанию не выполняет никаких действий. Он должен реализовать самостоятельно. Переопределите эту функцию, если вы хотите производит их особой обработки при обработке запроса для размера объекта OLE.

##  <a name="onhide"></a>  COleServerItem::OnHide

Вызвано структурой для скрытия элемента OLE.

```
virtual void OnHide();
```

### <a name="remarks"></a>Примечания

По умолчанию вызывает `COleServerDoc::OnShowDocument( FALSE )`. Функция также уведомляет контейнер, что была скрыта объекта OLE. Переопределите эту функцию, если вы хотите производит их особой обработки при скрытии объекта OLE.

##  <a name="oninitfromdata"></a>  COleServerItem::OnInitFromData

Вызывается платформой для инициализации объекта OLE, используя содержимое *pDataObject*.

```
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,
    BOOL bCreation);
```

### <a name="parameters"></a>Параметры

*pDataObject*<br/>
Указатель на объект данных OLE, содержащий данные в различных форматах для инициализации объекта OLE.

*bCreation*<br/>
Значение TRUE, если функция вызывается для инициализации объекта OLE, вновь создаваемого приложения-контейнера. Значение FALSE, если функция вызывается, чтобы заменить содержимое уже существующего элемента OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Если *bCreation* имеет значение TRUE, эта функция вызывается в том случае, если контейнер реализует вставить новый объект на основе текущего выделения. Данные, выбранные используется при создании нового объекта OLE. Например, если выделение диапазона ячеек в электронных таблицах, а затем создать диаграмму с помощью вставки нового объекта на основе значений в выбранном диапазоне. Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию, чтобы выбрать допустимый формат по сравнению с предлагаемой *pDataObject* и инициализации объекта OLE, на основе предоставленных данных. Существует расширенная переопределяемый.

Дополнительные сведения см. в разделе [IOleObject::InitFromData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-initfromdata) в пакете Windows SDK.

##  <a name="onopen"></a>  COleServerItem::OnOpen

Вызывается платформой для отображения объекта OLE в отдельном экземпляре серверного приложения, а не на месте.

```
virtual void OnOpen();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию активирует первое окно фрейма, отображение документа, содержащего объекта OLE; Если приложение является мини-сервера, реализация по умолчанию показано главное окно. Функция также уведомляет контейнер, что был открыт объекта OLE.

Переопределите эту функцию, если вы хотите производит их особой обработки при открытии объекта OLE. Это особенно часто, с которой вы хотите установить выделение по ссылке, при открытии связанных элементов.

Дополнительные сведения см. в разделе [IOleClientSite::OnShowWindow](/windows/desktop/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow) в пакете Windows SDK.

##  <a name="onqueryupdateitems"></a>  COleServerItem::OnQueryUpdateItems

Вызывается платформой для определения устаревших связанных элементов в текущем документе сервера.

```
virtual BOOL OnQueryUpdateItems();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ имеет элементы, требующие обновления; 0, если все элементы находятся в актуальном состоянии.

### <a name="remarks"></a>Примечания

Элемент является устаревшим, если его исходный документ был изменен, но связанный элемент не был обновлен для отражения изменений в документе.

##  <a name="onrenderdata"></a>  COleServerItem::OnRenderData

Вызывается платформой для извлечения данных в указанном формате.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структура, задающая формат, в котором запрашиваются сведения.

*lpStgMedium*<br/>
Указывает на [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) структуры, в котором они должны быть возвращены.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Указанный формат входит один ранее размещен в `COleDataSource` с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) или [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) функция-член для отложенной подготовки к просмотру. Реализация по умолчанию эта функция вызывает [OnRenderFileData](#onrenderfiledata) или [OnRenderGlobalData](#onrenderglobaldata), соответственно, если предоставленный среда хранения представляет собой файл или в памяти. Если ни один из этих форматов, реализация по умолчанию возвращает значение 0 и не выполняет никаких действий.

Если *lpStgMedium*-> *tymed* является TYMED_NULL, STGMEDIUM следует выделяется и заполняется в соответствии с *lpFormatEtc "->" tymed*. В противном случае TYMED_NULL, STGMEDIUM должно быть заполнено на месте с данными.

Существует расширенная переопределяемый. Переопределите эту функцию для предоставления данных в затребованном формате и средний. В зависимости от данных может потребоваться переопределить один из других версий эта функция вместо этого. Если данные находятся в малых и фиксированный размер, переопределить `OnRenderGlobalData`. Если данные находятся в файле, или имеет переменный размер, переопределить `OnRenderFileData`.

Дополнительные сведения см. в разделе [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc), и [TYMED](/windows/desktop/api/objidl/ne-objidl-tagtymed) в пакете Windows SDK.

##  <a name="onrenderfiledata"></a>  COleServerItem::OnRenderFileData

Вызывается платформой для извлечения данных в указанном формате в том случае, если среда хранения представляет собой файл.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структура, задающая формат, в котором запрашиваются сведения.

*pFile*<br/>
Указывает на `CFile` объект, в котором должен быть прорисован данные.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Указанный формат входит один ранее размещен в `COleDataSource` с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) функция-член для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает значение FALSE.

Существует расширенная переопределяемый. Переопределите эту функцию для предоставления данных в затребованном формате и средний. В зависимости от данных может потребоваться переопределить один из других версий эта функция вместо этого. Если вы хотите обрабатывать несколько решений по хранению данных, переопределить [OnRenderData](#onrenderdata). Если данные находятся в файле, или имеет переменный размер, переопределить [OnRenderFileData](#onrenderfiledata).

Дополнительные сведения см. в разделе [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) и [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) в пакете Windows SDK.

##  <a name="onrenderglobaldata"></a>  COleServerItem::OnRenderGlobalData

Вызывается платформой для извлечения данных в указанном формате, при глобальной памяти, заданную среду хранения.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структура, задающая формат, в котором запрашиваются сведения.

*phGlobal*<br/>
Указывает дескриптор глобальной памяти, в котором они должны быть возвращены. Если памяти не будет выделена, этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Указанный формат входит один ранее размещен в `COleDataSource` с помощью [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) функция-член для отложенной подготовки к просмотру. Реализация по умолчанию эта функция просто возвращает значение FALSE.

Если *phGlobal* имеет значение NULL, то новый HGLOBAL должен выделить и возвращены в *phGlobal*. В противном случае HGLOBAL определяемое *phGlobal* должно быть заполнено данными. Объем данных, помещаются в HGLOBAL не должен превышать текущий размер блока памяти. Кроме того блок не может быть перемещен большего размера.

Существует расширенная переопределяемый. Переопределите эту функцию для предоставления данных в затребованном формате и средний. В зависимости от данных может потребоваться переопределить один из других версий эта функция вместо этого. Если вы хотите обрабатывать несколько решений по хранению данных, переопределить [OnRenderData](#onrenderdata). Если данные находятся в файле, или имеет переменный размер, переопределить [OnRenderFileData](#onrenderfiledata).

Дополнительные сведения см. в разделе [IDataObject::GetData](/windows/desktop/api/objidl/nf-objidl-idataobject-getdata) и [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) в пакете Windows SDK.

##  <a name="onsetcolorscheme"></a>  COleServerItem::OnSetColorScheme

Вызывается платформой для указания цветовую палитру для использования при редактировании объекта OLE.

```
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```

### <a name="parameters"></a>Параметры

*lpLogPalette*<br/>
Указатель на Windows [LOGPALETTE](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette) структуры.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если используется цветовая палитра; в противном случае 0.

### <a name="remarks"></a>Примечания

Если приложение-контейнер был записан с помощью библиотеки Microsoft Foundation Class, эта функция вызывается, когда [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) функция соответствующего `COleClientItem` вызова объекта. Реализация по умолчанию возвращает значение FALSE. Переопределите эту функцию, если вы хотите использовать рекомендованную палитру. Серверное приложение не требуется использовать предлагаемый палитру.

Дополнительные сведения см. в разделе [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) в пакете Windows SDK.

##  <a name="onsetdata"></a>  COleServerItem::OnSetData

Вызывается платформой для замены данных объекта OLE с заданными данными.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указатель на [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc) структуры, указывающий формат данных.

*lpStgMedium*<br/>
Указатель на [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium) структуры, в которой хранятся данные.

*bRelease*<br/>
Указывает, кто является владельцем среды хранения после завершения вызова функции. Вызывающая сторона решает, кто отвечает за освобождение ресурсов, выделенной среду хранения. Вызывающий объект устанавливается не *bRelease*. Если *bRelease* — не равно нулю, серверный элемент принимает владение, освободить среду после завершения его использования. Когда *bRelease* равно 0, вызывающий объект сохраняет владение и элементом сервера можно использовать среду хранения только на протяжении всего вызова.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Элемент сервера вступают в владение данных он успешно получил его. То есть он не стать владельцем возвращается 0. Если источник данных принимает владельца, он освобождает среду хранения, вызвав [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) функции.

Реализация по умолчанию не выполняет никаких действий. Переопределите эту функцию, чтобы заменить данные объекта OLE с заданными данными. Существует расширенная переопределяемый.

Дополнительные сведения см. в разделе [STGMEDIUM](/windows/desktop/api/objidl/ns-objidl-tagstgmedium), [FORMATETC](/windows/desktop/api/objidl/ns-objidl-tagformatetc), и [ReleaseStgMedium](/windows/desktop/api/ole2/nf-ole2-releasestgmedium) в пакете Windows SDK.

##  <a name="onsetextent"></a>  COleServerItem::OnSetExtent

Вызывается платформой для сообщения элементу OLE, сколько места доступно на него в документе-контейнере.

```
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,
    const CSize& size);
```

### <a name="parameters"></a>Параметры

*nDrawAspect*<br/>
Указывает пропорции объекта OLE, границы которого были указаны. Этот параметр может иметь любой из следующих значений:

- Элемент DVASPECT_CONTENT представлен таким образом, что он может отображаться в виде внедренного объекта внутри контейнера.

- DVASPECT_THUMBNAIL будет отображен в представлении «эскиз», чтобы она может отображаться в средствах просмотра.

- Элемент DVASPECT_ICON представлен значком.

- Элемент DVASPECT_DOCPRINT представляется так, как если бы печати с помощью команды "Печать" меню "файл".

*size*<br/>
Объект [CSize](../../atl-mfc-shared/reference/csize-class.md) структуру, указав новый размер объекта OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Если приложение-контейнер был записан с помощью библиотеки Microsoft Foundation Class, эта функция вызывается, когда [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) функция-член соответствующего `COleClientItem` вызова объекта. Наборы данных для реализации по умолчанию [m_sizeExtent](#m_sizeextent) член до заданного размера Если *nDrawAspect* является DVASPECT_CONTENT; в противном случае возвращается 0. Переопределите эту функцию, чтобы выполнять специальную обработку при изменении размера элемента.

##  <a name="onshow"></a>  COleServerItem::OnShow

Вызывается платформой для указания серверное приложение для отображения объекта OLE на месте.

```
virtual void OnShow();
```

### <a name="remarks"></a>Примечания

Эта функция обычно вызывается, когда пользователь приложения-контейнера, создает элемент, или выполняет команды, например редактирование, который необходимо, чтобы элемент будет отображаться. Реализация по умолчанию пытается выполнить активацию на месте. Если это не удается, эта функция вызывает `OnOpen` функцию-член для отображения объекта OLE в отдельном окне.

Переопределите эту функцию, если вы хотите выполнять специальную обработку при отображении элемента OLE.

##  <a name="onupdate"></a>  COleServerItem::OnUpdate

Вызывается платформой при изменении элемента.

```
virtual void OnUpdate(
    COleServerItem* pSender,
    LPARAM lHint,
    CObject* pHint,
    DVASPECT nDrawAspect);
```

### <a name="parameters"></a>Параметры

*pSender*<br/>
Указатель на элемент, измененный документ. Может иметь значение NULL.

*lHint*<br/>
Содержит сведения об изменении.

*pHint*<br/>
Указатель на объект хранения сведения об изменении.

*nDrawAspect*<br/>
Значение из перечисления DVASPECT. Этот параметр может иметь одно из следующих значений:

- Элемент DVASPECT_CONTENT представлен таким образом, что он может отображаться в виде внедренного объекта внутри контейнера.

- DVASPECT_THUMBNAIL будет отображен в представлении «эскиз», чтобы она может отображаться в средствах просмотра.

- Элемент DVASPECT_ICON представлен значком.

- Элемент DVASPECT_DOCPRINT представляется так, как если бы печати с помощью команды "Печать" меню "файл".

### <a name="remarks"></a>Примечания

По умолчанию реализация вызывает [NotifyChanged](#notifychanged), независимо от подсказок или отправитель.

##  <a name="onupdateitems"></a>  COleServerItem::OnUpdateItems

Вызывается платформой для обновления всех элементов на серверном документе.

```
virtual void OnUpdateItems();
```

### <a name="remarks"></a>Примечания

По умолчанию реализация вызывает [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) для всех `COleClientItem` объектов в документе.

##  <a name="setitemname"></a>  COleServerItem::SetItemName

Вызывайте эту функцию при создании связанный элемент, чтобы задать его имя.

```
void SetItemName(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Параметры

*lpszItemName*<br/>
Указатель на новое имя элемента.

### <a name="remarks"></a>Примечания

Имя должно быть уникальным в пределах документа. При вызове серверного приложения для редактирования связанный элемент, приложение использует это имя для поиска элемента. Необходимо вызвать эту функцию для встроенных элементов.

## <a name="see-also"></a>См. также

[Пример MFC HIERSVR](../../visual-cpp-samples.md)<br/>
[Класс CDocItem](../../mfc/reference/cdocitem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс COleServerDoc](../../mfc/reference/coleserverdoc-class.md)<br/>
[Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
