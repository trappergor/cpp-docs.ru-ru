---
title: Класс ColeServerItem
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
ms.openlocfilehash: bdb91168a7c0ae718ca7d7514448b55965186aa8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753740"
---
# <a name="coleserveritem-class"></a>Класс ColeServerItem

Предоставляет серверный интерфейс элементам OLE.

## <a name="syntax"></a>Синтаксис

```
class COleServerItem : public CDocItem
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeServerItem::COleServerItem](#coleserveritem)|Формирует объект `COleServerItem`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeServerItem::AddOtherClipboardData](#addotherclipboarddata)|Размещает форматы презентации и преобразования в объекте. `COleDataSource`|
|[ColeServerItem:CopytoClipboard](#copytoclipboard)|Копирует элемент в Clipboard.|
|[ColeServerItem::DoDragDrop](#dodragdrop)|Выполняет операцию перетаскивания и падения.|
|[ColeServerItem::GetClipboardData](#getclipboarddata)|Получает источник данных для использования в передаче данных (перетаскивание и падение или Clipboard).|
|[ColeServerItem::GetDocument](#getdocument)|Возвращает серверный документ, содержащий элемент.|
|[ColeServerItem::GetEmbedSourceData](#getembedsourcedata)|Получает данные CF_EMBEDSOURCE для элемента OLE.|
|[ColeServerItem::GetItemName](#getitemname)|Возвращает имя элемента. Используется только для связанных элементов.|
|[ColeServerItem::GetLinkSourceData](#getlinksourcedata)|Получает CF_LINKSOURCE данных для элемента OLE.|
|[ColeServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|Получает данные CF_OBJECTDESCRIPTOR для элемента OLE.|
|[ColeServerItem::Отключено](#isconnected)|Указывает, присоединен ли элемент в настоящее время к активному контейнеру.|
|[ColeServerItem::IsLinkedItem](#islinkeditem)|Указывает, является ли элемент связанным элементом OLE.|
|[COleServerItem::NotifyChanged](#notifychanged)|Обновляет все контейнеры с автоматическим обновлением ссылки.|
|[ColeServerItem::OndoVerb](#ondoverb)|Призван выполнить глагол.|
|[ColeServerItem::Ondraw](#ondraw)|Вызывается, когда контейнер просит нарисовать элемент; реализации требуется.|
|[ColeServerItem::OndrawEx](#ondrawex)|Вызывается для специализированного чертежа элементов.|
|[ColeServerItem::OnGetClipboardData](#ongetclipboarddata)|Вызывается по системе, чтобы получить данные, которые будут скопированы на Clipboard.|
|[ColeServeritem::Ongetextent](#ongetextent)|Вызывается по фреймворку, чтобы получить размер элемента OLE.|
|[ColeServerItem::OnInitFromData](#oninitfromdata)|Вызывается рамкой для инициализации элемента OLE с использованием содержимого указанного объекта передачи данных.|
|[ColeServerItem::OnqueryupdateItems](#onqueryupdateitems)|Вызывается, чтобы определить, требуют ли какие-либо связанные элементы обновлять.|
|[ColeServeritem::OnRenderData](#onrenderdata)|Извлекает данные в рамках задержки рендеринга.|
|[ColeServeritem::OnrenderFileData](#onrenderfiledata)|Извлекает данные `CFile` в объект в рамках задержки рендеринга.|
|[ColeServeritem::OnrenderGlobalData](#onrenderglobaldata)|Извлекает данные в HGLOBAL в рамках задержки рендеринга.|
|[ColeServeritem::OnsetcolorScheme](#onsetcolorscheme)|Вызывается, чтобы установить цветовую схему предмета.|
|[ColeServeritem::OnsetData](#onsetdata)|Вызывается для установки данных элемента.|
|[ColeServeritem::Onsetextent](#onsetextent)|Вызывается по фрейму, чтобы установить размер элемента OLE.|
|[ColeServerItem::OnUpdate](#onupdate)|Вызывается при изменении части документа, в которой принадлежит элемент.|
|[ColeServerItem::OnUpdateItems](#onupdateitems)|Вызывается для обновления кэша презентации всех элементов в серверном документе.|
|[ColeServerItem::SetItemName](#setitemname)|Устанавливает название элемента. Используется только для связанных элементов.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[COleServerItem::GetDataИсточник](#getdatasource)|Получает объект, используемый для хранения форматов конверсии.|
|[ColeServerItem::OnHide](#onhide)|Вызывается по фрейму, чтобы скрыть элемент OLE.|
|[ColeServerItem::OnOpen](#onopen)|Вызывается фреймворцом для отображения элемента OLE в собственном окне верхнего уровня.|
|[ColeServerItem::Onshow](#onshow)|Вызывается при запросе контейнера, чтобы показать элемент.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleServerItem:::m_sizeExtent](#m_sizeextent)|Информирует сервер о том, сколько элемента OLE отображается.|

## <a name="remarks"></a>Remarks

Связанный элемент может представлять часть или весь серверный документ. Встроенный элемент всегда представляет собой весь серверный документ.

Класс `COleServerItem` определяет несколько переизликвых функций-членов, которые называются библиотеками динамической связи системы OLE (DLL), как правило, в ответ на запросы контейнерного приложения. Эти функции члена позволяют контейнерному приложению манипулировать элементом косвенно различными способами, например, отображая его, исполняя его глаголы или извлекая его данные в различных форматах.

Для `COleServerItem`использования, получения класса из него и реализации функций участника [OnDraw](#ondraw) и [Serialize.](../../mfc/reference/cobject-class.md#serialize) Функция `OnDraw` обеспечивает изображение метафайла элемента, что позволяет отображать его при открытии контейнерного приложения. Функция `Serialize` `CObject` обеспечивает родное представление элемента, позволяя передавать встроенный элемент между серверными и контейнерными приложениями. [OnGetExtent](#ongetextent) предоставляет естественный размер элемента контейнеру, позволяя контейнеру размер элемента.

Для получения дополнительной информации о серверах и смежных темах смотрите статью [«Серверы: Реализация сервера»](../../mfc/servers-implementing-a-server.md) и «Создание контейнерного/серверного приложения» в статье [Контейнеры: Расширенные возможности](../../mfc/containers-advanced-features.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

`COleServerItem`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coleserveritemaddotherclipboarddata"></a><a name="addotherclipboarddata"></a>ColeServerItem::AddOtherClipboardData

Вызовите эту функцию для размещения форматов представления `COleDataSource` и преобразования для элемента OLE в указанном объекте.

```cpp
void AddOtherClipboardData(COleDataSource* pDataSource);
```

### <a name="parameters"></a>Параметры

*pDataИсточник*<br/>
Указатель на `COleDataSource` объект, в котором должны быть размещены данные.

### <a name="remarks"></a>Remarks

Необходимо, чтобы функция участника [OnDraw](#ondraw) предоставила формат презентации (изображение метафайла) для элемента. Чтобы поддержать другие форматы конверсий, зарегистрируйте их с помощью объекта [COleDataSource,](../../mfc/reference/coledatasource-class.md) возвращенного [GetDataSource,](#getdatasource) и переопределить функцию участника [OnRenderData](#onrenderdata) для предоставления данных в форматах, которые вы хотите поддерживать.

## <a name="coleserveritemcoleserveritem"></a><a name="coleserveritem"></a>ColeServerItem::COleServerItem

Строит `COleServerItem` объект и добавляет его в коллекцию элементов документа серверного документа.

```
COleServerItem(
    COleServerDoc* pServerDoc,
    BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*pServerDoc*<br/>
Указатель на документ, который будет содержать новый элемент.

*bAutoDelete*<br/>
Пометить, может ли объект быть удален при освобождении ссылки на него. Установите это на `COleServerItem` FALSE, если объект является неотъемлемой частью данных документа, которые необходимо удалить. Установите это в истину, если объект является вторичной структурой, используемой для определения диапазона данных документа, которые могут быть удалены инфраструктурой.

## <a name="coleserveritemcopytoclipboard"></a><a name="copytoclipboard"></a>ColeServerItem:CopytoClipboard

Вызовите эту функцию, чтобы скопировать элемент OLE в Clipboard.

```cpp
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```

### <a name="parameters"></a>Параметры

*bIncludeLink*<br/>
Установите это в правду, если ссылка данные должны быть скопированы на Clipboard. Установите это на FALSE, если приложение сервера не поддерживает ссылки.

### <a name="remarks"></a>Remarks

Функция использует функцию члена [OnGetClipboardData](#ongetclipboarddata) для создания объекта [COleDataSource,](../../mfc/reference/coledatasource-class.md) содержащего данные элемента OLE в поддерживаемых форматах. Функция затем помещает `COleDataSource` объект на Clipboard с помощью функции [COleDataSource::SetClipboard.](../../mfc/reference/coledatasource-class.md#setclipboard) Объект `COleDataSource` включает в себя родные данные элемента и его представление в формате CF_METAFILEPICT, а также данные в любых форматах конверсии, которые вы выбираете для поддержки. Необходимо, чтобы функция [Serialize](../../mfc/reference/cobject-class.md#serialize) и [OnDraw](#ondraw) была реализована.

## <a name="coleserveritemdodragdrop"></a><a name="dodragdrop"></a>ColeServerItem::DoDragDrop

Вызов `DoDragDrop` функции участника для выполнения операции перетаскивания.

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
Прямоугольник элемента на экране, в пикселях, относительно области клиента.

*ptOffset*<br/>
Смещение от *lpItemRect,* где положение мыши было во время перетаскивания.

*bIncludeLink*<br/>
Установите это в правду, если ссылка данные должны быть скопированы на Clipboard. Установите его на FALSE, если приложение не поддерживает ссылки.

*dwEffects*<br/>
Определяет эффекты, которые источник перетаскивания позволит в операции перетаскивания (комбинация Copy, Move и Link).

*lpRectStartDrag*<br/>
Указатель на прямоугольник, который определяет, где на самом деле начинается сопротивление. Дополнительные сведения см. в разделе "Примечания".

### <a name="return-value"></a>Возвращаемое значение

Значение из перечисления DROPEFFECT. Если это DROPEFFECT_MOVE, исходные данные должны быть удалены.

### <a name="remarks"></a>Remarks

Операция перетаскивания начинается не сразу. Он ждет, пока курсор мыши не покинет прямоугольник, указанный *lpRectStartDrag,* или до тех пор, пока не пройдет определенное количество миллисекунд. Если *lpRectStartDrag* является NULL, прямоугольник по умолчанию используется так, что перетащите начинается, когда курсор мыши перемещает один пиксель.

Время задержки определяется параметром ключа реестра. Вы можете изменить время задержки, позвонив [в CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring) или [CWinApp::WriteProfileInt](../../mfc/reference/cwinapp-class.md#writeprofileint). Если вы не указали время задержки, используется значение по умолчанию 200 миллисекунд. Время задержки перетаскивания сохраняется следующим образом:

- Время задержки Windows NT Drag хранится в HKEY_LOCAL_MACHINE»SOFTWARE-Microsoft-Windows-NT-CurrentVersion-IniFileMapping-win.ini-Windows-DragDelay.

- Время задержки Windows 3.x Перетащите сохраняется в WIN. Файл INI, в разделе «Окна».

- Время задержки Windows 95/98 перетащите хранится в кэшированной версии WIN. Ini.

Для получения дополнительной информации о том, как информация о задержке перетаскивания хранится в реестре или . INI файл, [см. WriteProfileString](/windows/win32/api/winbase/nf-winbase-writeprofilestringw) в Windows SDK.

## <a name="coleserveritemgetclipboarddata"></a><a name="getclipboarddata"></a>ColeServerItem::GetClipboardData

Вызовите эту функцию, чтобы заполнить указанный объект [COleDataSource](../../mfc/reference/coledatasource-class.md) со всеми данными, которые будут скопированы на clipboard, если вы называете [CopyToClipboard](#copytoclipboard) (те же данные также будут переданы, если вы называете [DoDragDrop](#dodragdrop)).

```cpp
void GetClipboardData(
    COleDataSource* pDataSource,
    BOOL bIncludeLink = FALSE,
    LPPOINT lpOffset = NULL,
    LPSIZE lpSize = NULL);
```

### <a name="parameters"></a>Параметры

*pDataИсточник*<br/>
Указатель на `COleDataSource` объект, который будет получать данные элемента OLE во всех поддерживаемых форматах.

*bIncludeLink*<br/>
TRUE, если данные ссылки должны быть скопированы на Clipboard. FALSE, если приложение сервера не поддерживает ссылки.

*lpOffset*<br/>
Смещение, в пикселях, курсора мыши от происхождения объекта.

*lpSize*<br/>
Размер объекта в пикселях.

### <a name="remarks"></a>Remarks

Эта функция вызывает функцию члена [GetEmbedSourceData](#getembedsourcedata) для получения исходных данных для элемента OLE и вызывает функцию члена [AddOtherClipboardData,](#addotherclipboarddata) чтобы получить формат презентации и любые поддерживаемые форматы преобразования. Если *bIncludeLink* является правдой, функция также вызывает [GetLinkSourceData,](#getlinksourcedata) чтобы получить данные о ссылках для элемента.

Переопределить эту функцию, если вы `COleDataSource` хотите поместить форматы в `CopyToClipboard`объект до или после тех форматов, поставляемых .

## <a name="coleserveritemgetdatasource"></a><a name="getdatasource"></a>COleServerItem::GetDataИсточник

Вызовите эту функцию, чтобы получить объект [COleDataSource,](../../mfc/reference/coledatasource-class.md) используемый для хранения форматов преобразования, которые поддерживает серверное приложение.

```
COleDataSource* GetDataSource();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `COleDataSource` объект, используемый для хранения форматов преобразования.

### <a name="remarks"></a>Remarks

Если вы хотите, чтобы приложение сервера предлагало данные в различных форматах во время операций по передаче данных, зарегистрируйте эти форматы с объектом, `COleDataSource` возвращенным этой функцией. Например, если вы хотите предоставить CF_TEXT представление элемента OLE для операций Clipboard или перетаскивания, вы регистрируете формат с `COleDataSource` объектом, который эта функция возвращает, а затем переопределяет функцию `OnRenderXxxData` члена для предоставления данных.

## <a name="coleserveritemgetdocument"></a><a name="getdocument"></a>ColeServerItem::GetDocument

Вызовите эту функцию, чтобы получить указатель на документ, содержащий элемент.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, содержащий элемент; NULL, если элемент не является частью документа.

### <a name="remarks"></a>Remarks

Это позволяет получить доступ к серверу документа, `COleServerItem` который вы передали в качестве аргумента конструктору.

## <a name="coleserveritemgetembedsourcedata"></a><a name="getembedsourcedata"></a>ColeServerItem::GetEmbedSourceData

Вызовите эту функцию, чтобы получить CF_EMBEDSOURCE данные для элемента OLE.

```cpp
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*lpStgMedium*<br/>
Указатель на структуру [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) которая будет получать данные CF_EMBEDSOURCE для элемента OLE.

### <a name="remarks"></a>Remarks

Этот формат включает в себя родные данные элемента. Необходимо, чтобы `Serialize` функция члена работала должным образом.

Результат может быть добавлен в источник данных с помощью [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически [COleServerItem::OnGetClipboardData](#ongetclipboarddata).

Для получения дополнительной информации [см.](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)

## <a name="coleserveritemgetitemname"></a><a name="getitemname"></a>ColeServerItem::GetItemName

Вызовите эту функцию, чтобы получить имя элемента.

```
const CString& GetItemName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя элемента.

### <a name="remarks"></a>Remarks

Обычно эту функцию вызывают только для связанных элементов.

## <a name="coleserveritemgetlinksourcedata"></a><a name="getlinksourcedata"></a>ColeServerItem::GetLinkSourceData

Вызовите эту функцию, чтобы получить данные CF_LINKSOURCE для элемента OLE.

```
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*lpStgMedium*<br/>
Указатель на структуру [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) которая будет получать CF_LINKSOURCE данные для элемента OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Этот формат включает в себя CLSID, описывающий тип элемента OLE и информацию, необходимую для поиска документа, содержащего элемент OLE.

Результат может быть добавлен в источник данных с [COleDataSource::CacheData](../../mfc/reference/coledatasource-class.md#cachedata). Эта функция вызывается автоматически [OnGetClipboardData](#ongetclipboarddata).

Для получения дополнительной информации [см.](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)

## <a name="coleserveritemgetobjectdescriptordata"></a><a name="getobjectdescriptordata"></a>ColeServerItem::GetObjectDescriptorData

Вызовите эту функцию, чтобы получить CF_OBJECTDESCRIPTOR данные для элемента OLE.

```cpp
void GetObjectDescriptorData(
    LPPOINT lpOffset,
    LPSIZE lpSize,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*lpOffset*<br/>
Смещение щелчка мыши из верхнего левого угла элемента OLE. Может иметь значение NULL.

*lpSize*<br/>
Размер элемента OLE. Может иметь значение NULL.

*lpStgMedium*<br/>
Указатель на структуру [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) которая будет получать CF_OBJECTDESCRIPTOR данные для элемента OLE.

### <a name="remarks"></a>Remarks

Информация скопирована `STGMEDIUM` в структуру, на которую указывает *lpStgMedium*. Этот формат включает в себя информацию, необходимую для диалога Paste Special.

Для получения дополнительной информации [см.](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1)

## <a name="coleserveritemisconnected"></a><a name="isconnected"></a>ColeServerItem::Отключено

Вызовите эту функцию, чтобы увидеть, подключен ли элемент OLE.

```
BOOL IsConnected() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент подключен; в противном случае 0.

### <a name="remarks"></a>Remarks

Элемент OLE считается подключенным, если один или несколько контейнеров имеют ссылки на товар. Элемент подключается, если его количество ссылок превышает 0 или если он является встроенным элементом.

## <a name="coleserveritemislinkeditem"></a><a name="islinkeditem"></a>ColeServerItem::IsLinkedItem

Позвоните в эту функцию, чтобы увидеть, является ли элемент OLE связанным элементом.

```
BOOL IsLinkedItem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент является связанным элементом; в противном случае 0.

### <a name="remarks"></a>Remarks

Элемент связан, если элемент действителен и не возвращается в список встроенных элементов документа. Связанный элемент может или не может быть подключен к контейнеру.

Обычно используется один и тот же класс как для связанных, так и для встроенных элементов. `IsLinkedItem`позволяет заставить связанные элементы вести себя иначе, чем встроенные элементы, хотя во много раз код является общим.

## <a name="coleserveritemm_sizeextent"></a><a name="m_sizeextent"></a>COleServerItem:::m_sizeExtent

Этот элемент сообщает серверу, сколько объекта отображается в контейнерном документе.

```
CSize m_sizeExtent;
```

### <a name="remarks"></a>Remarks

Реализация [OnSetExtent](#onsetextent) по умолчанию устанавливает этот участник.

## <a name="coleserveritemnotifychanged"></a><a name="notifychanged"></a>COleServerItem::NotifyChanged

Вызовите эту функцию после изменения связанного элемента.

```cpp
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```

### <a name="parameters"></a>Параметры

*nDrawAspect*<br/>
Значение из перечисления DVASPECT, которое указывает, какой аспект элемента OLE изменился. Этот параметр может принимать любое из перечисленных ниже значений.

- DVASPECT_CONTENT Элемент представлен таким образом, что он может отображаться как встроенный объект внутри контейнера.

- DVASPECT_THUMBNAIL Элемент отображается в представлении "thumbnail", чтобы его можно было отображать в инструменте просмотра.

- DVASPECT_ICON Элемент представлен иконой.

- DVASPECT_DOCPRINT Элемент представлен так, как если бы он был напечатан с помощью команды Print из меню файла.

### <a name="remarks"></a>Remarks

Если элемент контейнера связан с документом с автоматической ссылкой, элемент обновляется с учетом изменений. В контейнерных приложениях, написанных с помощью библиотеки класса Microsoft Foundation, [COleClientItem::OnChange](../../mfc/reference/coleclientitem-class.md#onchange) вызывается в ответ.

## <a name="coleserveritemondoverb"></a><a name="ondoverb"></a>ColeServerItem::OndoVerb

Вызывается фреймворком для выполнения указанного глагола.

```
virtual void OnDoVerb(LONG iVerb);
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Определяет глагол для выполнения. Это может быть любой из следующих:

|Значение|Значение|Символ|
|-----------|-------------|------------|
|0|первичный глагол|OLEIVERB_PRIMARY|
|1|Вторичный глагол|(нет)|
|- 1|Элемент отображения для редактирования|OLEIVERB_SHOW|
|- 2|Элемент отсечения в отдельном окне|OLEIVERB_OPEN|
|- 3|Скрыть элемент|OLEIVERB_HIDE|

Значение -1 обычно является псевдонимом для другого глагола. Если открытое редактирование не поддерживается, -2 имеет тот же эффект, что и -1. Дополнительные значения можно узнать в SDK с мгновению [IOleObject::DoVerb.](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb)

### <a name="remarks"></a>Remarks

Если контейнерное приложение было написано в библиотеке класса Microsoft Foundation, эта функция называется `COleClientItem` при вызове [функции COleClientItem::Activate-функции](../../mfc/reference/coleclientitem-class.md#activate) соответствующего объекта. Реализация по умолчанию вызывает функцию члена [OnShow,](#onshow) если указан основной глагол или OLEIVERB_SHOW, [OnOpen,](#onopen) если указан вторичный глагол или OLEIVERB_OPEN, и [OnHide,](#onhide) если указанOLEIVERB_HIDE. Реализация по `OnShow` умолчанию вызывает, если *iVerb* не является одним из глаголов, перечисленных выше.

Переопределить эту функцию, если основной глагол не показывает элемент. Например, если элемент является звукозаписывающей звукозаписи и его основным глаголом является Play, вам не придется отображать серверное приложение для воспроизведения элемента.

Для получения дополнительной информации [см. IOleObject::DoVerb](/windows/win32/api/oleidl/nf-oleidl-ioleobject-doverb) в Windows SDK.

## <a name="coleserveritemondraw"></a><a name="ondraw"></a>ColeServerItem::Ondraw

Вызывается фреймворком для визирования элемента OLE в метафайл.

```
virtual BOOL OnDraw(
    CDC* pDC,
    CSize& rSize) = 0;
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на объект [CDC,](../../mfc/reference/cdc-class.md) на котором можно нарисовать элемент. Контекст отображения автоматически подключается к контексту отображения атрибута, так что вы можете вызвать функции атрибута, хотя это сделает метафильное устройство специфическим.

*rРазмер*<br/>
Размер, в единицах HIMETRIC, в которых рисовать метафайл.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент был успешно нарисован; в противном случае 0.

### <a name="remarks"></a>Remarks

Метафайлное представление элемента OLE используется для отображения элемента в контейнерном приложении. Если контейнерное приложение было написано в библиотеке класса Microsoft Foundation, метафайл используется функцией участника [Draw](../../mfc/reference/coleclientitem-class.md#draw) соответствующего объекта [COleClientItem.](../../mfc/reference/coleclientitem-class.md) Реализация по умолчанию отсутствует. Необходимо переопределить эту функцию, чтобы втянуть элемент в указанный контекст устройства.

## <a name="coleserveritemondrawex"></a><a name="ondrawex"></a>ColeServerItem::OndrawEx

Вызывается рамкой для всех чертежей.

```
virtual BOOL OnDrawEx(
    CDC* pDC,
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на объект [CDC,](../../mfc/reference/cdc-class.md) на котором можно нарисовать элемент. DC автоматически подключается к атрибуту DC, так что вы можете вызвать функции атрибута, хотя это сделает метафильное устройство специфическим.

*nDrawAspect*<br/>
Значение из перечисления DVASPECT. Этот параметр может принимать любое из перечисленных ниже значений.

- DVASPECT_CONTENT Элемент представлен таким образом, что он может отображаться как встроенный объект внутри контейнера.

- DVASPECT_THUMBNAIL Элемент отображается в представлении "thumbnail", чтобы его можно было отображать в инструменте просмотра.

- DVASPECT_ICON Элемент представлен иконой.

- DVASPECT_DOCPRINT Элемент представлен так, как если бы он был напечатан с помощью команды Print из меню файла.

*rРазмер*<br/>
Размер товара в единицах HIMETRIC.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент был успешно нарисован; в противном случае 0.

### <a name="remarks"></a>Remarks

Выполнение по `OnDraw` умолчанию вызывается, когда DVASPECT равен DVASPECT_CONTENT; в противном случае это не удается.

Переопределить эту функцию, чтобы предоставить данные презентации для не DVASPECT_CONTENT, таких как DVASPECT_ICON или DVASPECT_THUMBNAIL.

## <a name="coleserveritemongetclipboarddata"></a><a name="ongetclipboarddata"></a>ColeServerItem::OnGetClipboardData

Вызывается по системе, `COleDataSource` чтобы получить объект, содержащий все данные, которые будут размещены на Clipboard по вызову к функции члена [CopyToClipboard.](#copytoclipboard)

```
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,
    LPPOINT lpOffset,
    LPSIZE lpSize);
```

### <a name="parameters"></a>Параметры

*bIncludeLink*<br/>
Установите это в правду, если ссылка данные должны быть скопированы на Clipboard. Установите это на FALSE, если приложение сервера не поддерживает ссылки.

*lpOffset*<br/>
Смещение курсора мыши от происхождения объекта в пикселях.

*lpSize*<br/>
Размер объекта в пикселях.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [COleDataSource,](../../mfc/reference/coledatasource-class.md) содержащий данные Clipboard.

### <a name="remarks"></a>Remarks

Реализация этой функции по умолчанию вызывает [GetClipboardData.](#getclipboarddata)

## <a name="coleserveritemongetextent"></a><a name="ongetextent"></a>ColeServeritem::Ongetextent

Вызывается рамки для получения размера, в HIMETRIC единиц, элемента OLE.

```
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,
    CSize& rSize);
```

### <a name="parameters"></a>Параметры

*nDrawAspect*<br/>
Определяет сяокард элемента OLE, границы которого должны быть извлечены. Этот параметр может принимать любое из перечисленных ниже значений.

- DVASPECT_CONTENT Элемент представлен таким образом, что он может отображаться как встроенный объект внутри контейнера.

- DVASPECT_THUMBNAIL Элемент отображается в представлении "thumbnail", чтобы его можно было отображать в инструменте просмотра.

- DVASPECT_ICON Элемент представлен иконой.

- DVASPECT_DOCPRINT Элемент представлен так, как если бы он был напечатан с помощью команды Print из меню файла.

*rРазмер*<br/>
Ссылка `CSize` на объект, который получит размер элемента OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Если контейнерное приложение было написано в библиотеке класса Microsoft Foundation, эта `COleClientItem` функция вызывается при вызове функции участника [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent) соответствующего объекта. Реализация по умолчанию не выполняет никаких действий. Вы должны реализовать его самостоятельно. Переопределить эту функцию, если вы хотите выполнить специальную обработку при обработке запроса на размер элемента OLE.

## <a name="coleserveritemonhide"></a><a name="onhide"></a>ColeServerItem::OnHide

Вызывается по фрейму, чтобы скрыть элемент OLE.

```
virtual void OnHide();
```

### <a name="remarks"></a>Remarks

Вызовы `COleServerDoc::OnShowDocument( FALSE )`по умолчанию . Функция также уведомляет контейнер о том, что элемент OLE был скрыт. Переопределить эту функцию, если вы хотите выполнить специальную обработку при сокрытии элемента OLE.

## <a name="coleserveritemoninitfromdata"></a><a name="oninitfromdata"></a>ColeServerItem::OnInitFromData

Вызывается в рамках для инициализации элемента OLE с использованием содержимого *pDataObject*.

```
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,
    BOOL bCreation);
```

### <a name="parameters"></a>Параметры

*pDataObject*<br/>
Указатель на объект данных OLE, содержащий данные в различных форматах для инициализации элемента OLE.

*bCreation*<br/>
TRUE, если функция называется для инициализации элемента OLE, вновь созданного контейнерным приложением. FALSE, если функция называется для замены содержимого уже существующего элемента OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Если *bCreation* является правдой, эта функция называется, если контейнер реализует вставить новый объект на основе текущего выбора. Выбранные данные используются при создании нового элемента OLE. Например, при выборе диапазона ячеек в программе электронной таблицы, а затем с помощью вставки нового объекта для создания диаграммы, основанной на значениях в выбранном диапазоне. Реализация по умолчанию не выполняет никаких действий. Переопределить эту функцию, чтобы выбрать приемлемый формат из тех, которые предлагаются *pDataObject* и инициализировать элемент OLE на основе предоставленных данных. Это передовой overridable.

Для получения дополнительной информации [см. IOleObject::InitFromData](/windows/win32/api/oleidl/nf-oleidl-ioleobject-initfromdata) в Windows SDK.

## <a name="coleserveritemonopen"></a><a name="onopen"></a>ColeServerItem::OnOpen

Вызывается фреймворкдлям для отображения элемента OLE в отдельном экземпляре серверного приложения, а не на месте.

```
virtual void OnOpen();
```

### <a name="remarks"></a>Remarks

Реализация по умолчанию активирует окно первого кадра, отображающее документ, содержащий элемент OLE; если приложение является мини-сервером, реализация по умолчанию показывает основное окно. Функция также уведомляет контейнер об открытии элемента OLE.

Переопределить эту функцию, если вы хотите выполнить специальную обработку при открытии элемента OLE. Это особенно характерно для связанных элементов, где вы хотите установить выбор по ссылке, когда он открыт.

Для получения дополнительной информации, [см. IOleClientSite::OnShowWindow](/windows/win32/api/oleidl/nf-oleidl-ioleclientsite-onshowwindow) в Windows SDK.

## <a name="coleserveritemonqueryupdateitems"></a><a name="onqueryupdateitems"></a>ColeServerItem::OnqueryupdateItems

Вызывается в рамках, чтобы определить, являются ли какие-либо связанные элементы в текущем серверном документе устаревшими.

```
virtual BOOL OnQueryUpdateItems();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если документ содержит элементы, нуждающиеся в обновлении; 0, если все элементы обновлены.

### <a name="remarks"></a>Remarks

Элемент устарел, если его исходный документ был изменен, но связанный элемент не был обновлен, чтобы отразить изменения в документе.

## <a name="coleserveritemonrenderdata"></a><a name="onrenderdata"></a>ColeServeritem::OnRenderData

Вызывается рамкой для извлечения данных в указанном формате.

```
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) с указанием формата, в котором запрашивается информация.

*lpStgMedium*<br/>
Указывает на структуру [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) в которой данные должны быть возвращены.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Указанный формат — это `COleDataSource` тот, который ранее размещался в объекте с использованием функции члена [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) или [DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata) для задержки рендеринга. Реализация этой функции по умолчанию вызывает [OnRenderFileData](#onrenderfiledata) или [OnRenderGlobalData,](#onrenderglobaldata)соответственно, если поставляемый носитель хранения является либо файлом, либо памятью. Если ни один из этих форматов не поставляется, реализация по умолчанию возвращает 0 и ничего не делает.

Если *lpGMedium*-> *тимед* TYMED_NULL, STGMEDIUM должен выделяться и заполняться в том виде, в каком указано *lpFormatEtc->.* Если не TYMED_NULL, STGMEDIUM должны быть заполнены на месте с данными.

Это передовой overridable. Переопределить эту функцию, чтобы предоставить данные в запрашиваемом формате и среде. В зависимости от ваших данных, вы можете переопределить одну из других версий этой функции вместо этого. Если ваши данные малы и фиксированные по размеру, переопределить. `OnRenderGlobalData` Если данные находится в файле или имеют `OnRenderFileData`переменный размер, переопределить .

Для получения дополнительной информации [см. IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata), [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1), [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc), и [TYMED](/windows/win32/api/objidl/ne-objidl-tymed) в Windows SDK.

## <a name="coleserveritemonrenderfiledata"></a><a name="onrenderfiledata"></a>ColeServeritem::OnrenderFileData

Вызывается инфраструктурой для извлечения данных в указанном формате, когда среда хранения является файлом.

```
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,
    CFile* pFile);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) с указанием формата, в котором запрашивается информация.

*pFile*<br/>
Указывает на `CFile` объект, в котором должны быть визуализированы данные.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Указанный формат предварительно размещен `COleDataSource` в объекте с использованием функции члена [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) для задержки рендеринга. Реализация этой функции по умолчанию просто возвращает FALSE.

Это передовой overridable. Переопределить эту функцию, чтобы предоставить данные в запрашиваемом формате и среде. В зависимости от ваших данных, вы можете переопределить одну из других версий этой функции вместо этого. Если вы хотите обрабатывать несколько носителей хранения, переопределить [OnRenderData.](#onrenderdata) Если данные находится в файле или имеют переменный размер, переопределить [OnRenderFileData.](#onrenderfiledata)

Для получения дополнительной информации см. [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) и [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

## <a name="coleserveritemonrenderglobaldata"></a><a name="onrenderglobaldata"></a>ColeServeritem::OnrenderGlobalData

Вызывается фреймворцом для извлечения данных в указанном формате, когда указанная среда хранения является глобальной памятью.

```
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,
    HGLOBAL* phGlobal);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указывает на структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) с указанием формата, в котором запрашивается информация.

*phGlobal*<br/>
Указывает на ручку глобальной памяти, в которой данные должны быть возвращены. Если память не выделена, этот параметр может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Указанный формат предварительно размещен `COleDataSource` в объекте с использованием функции члена [DelayRenderData](../../mfc/reference/coledatasource-class.md#delayrenderdata) для задержки рендеринга. Реализация этой функции по умолчанию просто возвращает FALSE.

Если *phGlobal* является NULL, то новый HGLOBAL должен быть выделен и возвращен в *phGlobal*. В противном случае HGLOBAL, указанный *phGlobal,* должен быть заполнен данными. Объем данных, размещенных в HGLOBAL, не должен превышать текущий размер блока памяти. Кроме того, блок не может быть перераспределен в больший размер.

Это передовой overridable. Переопределить эту функцию, чтобы предоставить данные в запрашиваемом формате и среде. В зависимости от ваших данных, вы можете переопределить одну из других версий этой функции вместо этого. Если вы хотите обрабатывать несколько носителей хранения, переопределить [OnRenderData.](#onrenderdata) Если данные находится в файле или имеют переменный размер, переопределить [OnRenderFileData.](#onrenderfiledata)

Для получения дополнительной информации см. [IDataObject::GetData](/windows/win32/api/objidl/nf-objidl-idataobject-getdata) и [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) в Windows SDK.

## <a name="coleserveritemonsetcolorscheme"></a><a name="onsetcolorscheme"></a>ColeServeritem::OnsetcolorScheme

Вызывается в рамках, чтобы указать цветовую палитру, которая будет использоваться при редактировании элемента OLE.

```
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```

### <a name="parameters"></a>Параметры

*lpLogPalette*<br/>
Указатель на структуру Windows [LOGpalette.](/windows/win32/api/wingdi/ns-wingdi-logpalette)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если используется цветовая палитра; в противном случае 0.

### <a name="remarks"></a>Remarks

Если контейнерное приложение было написано с помощью библиотеки класса Microsoft Foundation, эта функция `COleClientItem` называется при вызове функции [IOleObject::SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) соответствующего объекта. Реализация по умолчанию возвращает FALSE. Переопределить эту функцию, если вы хотите использовать рекомендуемую палитру. Серверное приложение не обязано использовать предложенную палитру.

Для получения дополнительной информации [см. IOleObject::SetColorScheme](/windows/win32/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) в Windows SDK.

## <a name="coleserveritemonsetdata"></a><a name="onsetdata"></a>ColeServeritem::OnsetData

Вызывается рамкой для замены данных элемента OLE на указанные данные.

```
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,
    LPSTGMEDIUM lpStgMedium,
    BOOL bRelease);
```

### <a name="parameters"></a>Параметры

*lpFormatEtc*<br/>
Указатель на структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) с указанием формата данных.

*lpStgMedium*<br/>
Указатель на структуру [STGMEDIUM,](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1) в которой находятся данные.

*bRelease*<br/>
Указывает, кто владеет носителем хранения после завершения вызова функции. Звонящий решает, кто несет ответственность за выделение ресурсов, выделенных от имени носителя. Вызывающий абонент делает это, установив *bRelease.* Если *bRelease* является ненулевой, элемент сервера приобретает право собственности, освобождая среду, когда он закончил использовать его. Когда *bRelease* равен 0, абонент сохраняет право собственности, а элемент сервера может использовать среду хранения только на время вызова.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Элемент сервера не берет на себя ответственность за данные до тех пор, пока он не успешно получил их. То есть, он не берет на себя ответственность, если он возвращает 0. Если источник данных берет на себя право собственности, он освобождает среду хранения, позвонив в функцию [ReleaseStgMedium.](/windows/win32/api/ole2/nf-ole2-releasestgmedium)

Реализация по умолчанию не выполняет никаких действий. Переопределить эту функцию, чтобы заменить данные элемента OLE с указанными данными. Это передовой overridable.

Для получения дополнительной информации, см [STGMEDIUM](/windows/win32/api/objidl/ns-objidl-ustgmedium~r1), [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc), и [ReleaseStgMedium](/windows/win32/api/ole2/nf-ole2-releasestgmedium) в Windows SDK.

## <a name="coleserveritemonsetextent"></a><a name="onsetextent"></a>ColeServeritem::Onsetextent

Вызывается по системе, чтобы сообщить элементу OLE, сколько места доступно для него в контейнерном документе.

```
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,
    const CSize& size);
```

### <a name="parameters"></a>Параметры

*nDrawAspect*<br/>
Определяется аспект элемента OLE, границы которого уточняются. Этот параметр может принимать любое из перечисленных ниже значений.

- DVASPECT_CONTENT Элемент представлен таким образом, что он может отображаться как встроенный объект внутри контейнера.

- DVASPECT_THUMBNAIL Элемент отображается в представлении "thumbnail", чтобы его можно было отображать в инструменте просмотра.

- DVASPECT_ICON Элемент представлен иконой.

- DVASPECT_DOCPRINT Элемент представлен так, как если бы он был напечатан с помощью команды Print из меню файла.

*size*<br/>
Структура [CSize](../../atl-mfc-shared/reference/csize-class.md) с указанием нового размера элемента OLE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Если контейнерное приложение было написано в библиотеке класса Microsoft Foundation, эта `COleClientItem` функция вызывается при вызове функции члена [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent) соответствующего объекта. Реализация по умолчанию устанавливает [m_sizeExtent](#m_sizeextent) член омичем, если *nDrawAspect* находится DVASPECT_CONTENT; в противном случае он возвращает 0. Переопределить эту функцию для выполнения специальной обработки при изменении размера элемента.

## <a name="coleserveritemonshow"></a><a name="onshow"></a>ColeServerItem::Onshow

Вызывается в рамках, чтобы поручить серверное приложение для отображения элемента OLE на месте.

```
virtual void OnShow();
```

### <a name="remarks"></a>Remarks

Эта функция обычно вызывается, когда пользователь контейнерного приложения создает элемент или выполняет глагол, например Edit, который требует отображаемого элемента. Реализация по умолчанию пытается активации на месте. Если это не удается, функция вызывает функцию `OnOpen` участника для отображения элемента OLE в отдельном окне.

Переизбь эту функцию, если вы хотите выполнить специальную обработку при отобрагивании элемента OLE.

## <a name="coleserveritemonupdate"></a><a name="onupdate"></a>ColeServerItem::OnUpdate

Вызывается фректовой при изменении элемента.

```
virtual void OnUpdate(
    COleServerItem* pSender,
    LPARAM lHint,
    CObject* pHint,
    DVASPECT nDrawAspect);
```

### <a name="parameters"></a>Параметры

*pСендер*<br/>
Указатель на элемент, который изменил документ. Может иметь значение NULL.

*lHint*<br/>
Содержит информацию об модификации.

*Phint*<br/>
Указатель на объект, хранящей информацию об модификации.

*nDrawAspect*<br/>
Значение из перечисления DVASPECT. Этот параметр может иметь любое из следующих значений:

- DVASPECT_CONTENT Элемент представлен таким образом, что он может отображаться как встроенный объект внутри контейнера.

- DVASPECT_THUMBNAIL Элемент отображается в представлении "thumbnail", чтобы его можно было отображать в инструменте просмотра.

- DVASPECT_ICON Элемент представлен иконой.

- DVASPECT_DOCPRINT Элемент представлен так, как если бы он был напечатан с помощью команды Print из меню файла.

### <a name="remarks"></a>Remarks

Реализация по умолчанию вызывает [Уведомление,](#notifychanged)независимо от подсказки или отправителя.

## <a name="coleserveritemonupdateitems"></a><a name="onupdateitems"></a>ColeServerItem::OnUpdateItems

Вызывается в рамках для обновления всех элементов в серверном документе.

```
virtual void OnUpdateItems();
```

### <a name="remarks"></a>Remarks

Реализация по умолчанию вызывает `COleClientItem` [UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink) для всех объектов документа.

## <a name="coleserveritemsetitemname"></a><a name="setitemname"></a>ColeServerItem::SetItemName

Вызовите эту функцию при создании связанного элемента, чтобы установить его имя.

```cpp
void SetItemName(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>Параметры

*lpszItemName*<br/>
Указатель на новое название элемента.

### <a name="remarks"></a>Remarks

Название должно быть уникальным в документе. Когда серверное приложение вызывается для отсвачения связанного элемента, приложение использует это имя для поиска элемента. Вам не нужно вызывать эту функцию для встроенных элементов.

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс CDocItem](../../mfc/reference/cdocitem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс ColeClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс ColeServerDoc](../../mfc/reference/coleserverdoc-class.md)<br/>
[Класс COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)
