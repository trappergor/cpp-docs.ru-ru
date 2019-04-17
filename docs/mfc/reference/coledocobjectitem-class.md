---
title: Класс COleDocObjectItem
ms.date: 11/04/2016
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
ms.openlocfilehash: 382960b4dc4dcfa61c836a87044dd14585756174
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769651"
---
# <a name="coledocobjectitem-class"></a>Класс COleDocObjectItem

Реализует хранение активных документов.

## <a name="syntax"></a>Синтаксис

```
class COleDocObjectItem : public COleClientItem
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Создает `COleDocObject` элемента.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Печать документа приложения-контейнера, используя параметры принтера по умолчанию.|
|[COleDocObjectItem::ExecCommand](#execcommand)|Выполняет команду, указанные пользователем.|
|[COleDocObjectItem::GetActiveView](#getactiveview)|Получает активное представление документа.|
|[COleDocObjectItem::GetPageCount](#getpagecount)|Возвращает число страниц в документе приложения-контейнера.|
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|Подготавливает приложения-контейнера документа для печати.|
|[COleDocObjectItem::OnPrint](#onprint)|Печать документа приложения-контейнера.|
|[COleDocObjectItem::QueryCommand](#querycommand)|Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.|
|[COleDocObjectItem::Release](#release)|Освобождает соединение для связанного элемента OLE и закрывается, если он был открыт. Уничтожает элемент клиента.|

## <a name="remarks"></a>Примечания

В MFC активном документе подобным образом распределяется регулярных месте, в редактируемой внедрения, со следующими отличиями:

- `COleDocument`-Производный класс по-прежнему поддерживает список в настоящее время внедренные элементы; тем не менее, это могут быть `COleDocObjectItem`-производных элементов.

- При активном в активном документе занимает всей клиентской области, представления, когда активен на месте.

- Контейнер активного документа обладает полным контролем над **помочь** меню.

- **Помочь** меню содержит элементы меню для контейнера активных документов и сервера.

Так как контейнер активного документа, которому принадлежит **помочь** меню контейнер отвечает за сервера пересылки **помочь** меню сообщения на сервер. Такая интеграция обрабатывается `COleDocObjectItem`.

Дополнительные сведения о путем слияния меню и активации активного документа, см. в разделе Обзор [вложение активного документа](../../mfc/active-document-containment.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

##  <a name="coledocobjectitem"></a>  COleDocObjectItem::COleDocObjectItem

Вызов этой функции-члена для инициализации `COleDocObjectItem` объекта.

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>Параметры

*pContainerDoc*<br/>
Указатель на `COleDocument` объект, действующий как контейнер активного документа. Этот параметр должен иметь значение NULL для разрешения implement_serialize. Обычно элементы OLE создаются с использованием указателя документа отличное от NULL.

##  <a name="dodefaultprinting"></a>  COleDocObjectItem::DoDefaultPrinting

Вызывается платформой для документа, используя параметры по умолчанию.

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Параметры

*pCaller*<br/>
Указатель на [CView](../../mfc/reference/cview-class.md) объект, который отправляет команды print.

*pInfo*<br/>
Указатель на [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) объект, который содержит описание задания печати.

##  <a name="execcommand"></a>  COleDocObjectItem::ExecCommand

Вызов этой функции-члена для выполнения команды, указанные пользователем.

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>Параметры

*nCmdID*<br/>
Идентификатор команды для выполнения. Должна входить в группу, идентифицируемый *параметром pguidCmdGroup*.

*nCmdExecOpt*<br/>
Указывает параметры выполнения команды. По умолчанию, чтобы выполнить команду без подтверждения пользователя. См. в разделе [перечислений OLECMDEXECOPT](/windows/desktop/api/docobj/ne-docobj-olecmdexecopt) список значений.

*pguidCmdGroup*<br/>
Уникальный идентификатор группы команд. По умолчанию NULL, которое указывает стандартной группы. Команда переданный *nCmdID* должны принадлежать к группе.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK, если выполнение прошло успешно; в противном случае возвращает одно из следующих кодов ошибки.

|Значение|Описание|
|-----------|-----------------|
|E_UNEXPECTED|Произошла непредвиденная ошибка.|
|E_FAIL|Произошла ошибка.|
|E_NOTIMPL|Указывает MFC сам должен попытаться перевести и отправлять команды.|
|OLECMDERR_E_UNKNOWNGROUP|*параметром pguidCmdGroup* не равно NULL, но не указывает на известную группу команд.|
|OLECMDERR_E_NOTSUPPORTED|*nCmdID* не является допустимой командой в pGroup группы.|
|OLECMDERR_DISABLED|Команда, указанная *nCmdID* отключена и не может быть выполнена.|
|OLECMDERR_NOHELP|Вызывающий объект и ответы для получения справки о команде, указанной *nCmdID* , но нет справочных сведений.|
|OLECMDERR_CANCELLED|Пользователь отменил выполнение.|

### <a name="remarks"></a>Примечания

*Параметром pguidCmdGroup* и *nCmdID* параметра однозначно определить команду, вызываемую. *NCmdExecOpt* параметр указывает точное действие, выполняемое.

##  <a name="getactiveview"></a>  COleDocObjectItem::GetActiveView

Вызов этой функции-члена для получения указателя на `IOleDocumentView` интерфейс текущему активному представлению.

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [IOleDocumentView](/windows/desktop/api/docobj/nn-docobj-ioledocumentview) интерфейс текущему активному представлению. Если нет текущего представления, возвращается значение NULL.

### <a name="remarks"></a>Примечания

Счетчик ссылок в возвращенном `IOleDocumentView` указатель не увеличивается, возвращаемую этой функцией.

##  <a name="getpagecount"></a>  COleDocObjectItem::GetPageCount

Вызовите эту функцию-член для извлечения нескольких страниц в документе.

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>Параметры

*pnFirstPage*<br/>
Указатель на номер первой страницы документа. Может иметь значение NULL, указывающее, что вызывающему объекту не требуется этот номер.

*pcPages*<br/>
Указатель на общее число страниц в документе. Может иметь значение NULL, указывающее, что вызывающему объекту не требуется этот номер.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="onprepareprinting"></a>  COleDocObjectItem::OnPreparePrinting

Эта функция-член вызывается платформой для подготовки к печати документа.

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Параметры

*pCaller*<br/>
Указатель на [CView](../../mfc/reference/cview-class.md) объект, который отправляет команды print.

*pInfo*<br/>
Указатель на [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) объект, который содержит описание задания печати.

*bPrintAll*<br/>
Указывает, является ли на печать всего документа.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="onprint"></a>  COleDocObjectItem::OnPrint

Эта функция-член вызывается платформой для печати документа.

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Параметры

*pCaller*<br/>
Указатель на объект CView, который отправляет команды print.

*pInfo*<br/>
Указатель на [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) объект, который содержит описание задания печати.

*bPrintAll*<br/>
Указывает, является ли на печать всего документа.

##  <a name="querycommand"></a>  COleDocObjectItem::QueryCommand

Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>Параметры

*nCmdID*<br/>
Идентификатор команды, для которого запрашивается.

*pdwStatus*<br/>
Указатель на флаги, возвращаемые в результате запроса. Список возможных значений см. в разделе [OLECMDF](/windows/desktop/api/docobj/ne-docobj-olecmdf).

*pCmdText*<br/>
Указатель на [OLECMDTEXT](/windows/desktop/api/docobj/ns-docobj-_tagolecmdtext) структуры, в которую будет возвращено имя и сведения о состоянии одной команды. Может иметь значение NULL, чтобы указать, что ему нужны эти сведения.

*pguidCmdGroup*<br/>
Уникальный идентификатор группы команд; может иметь значение NULL для указания стандартной группы.

### <a name="return-value"></a>Возвращаемое значение

Полный список возвращаемых значений, см. в разделе [IOleCommandTarget::QueryStatus](/windows/desktop/api/docobj/nf-docobj-iolecommandtarget-querystatus) в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности [IOleCommandTarget::QueryStatus](/windows/desktop/api/docobj/nf-docobj-iolecommandtarget-querystatus) метод, как описано в пакете Windows SDK.

##  <a name="release"></a>  COleDocObjectItem::Release

Освобождает соединение для связанного элемента OLE и закрывается, если он был открыт. Уничтожает элемент клиента.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>Параметры

*dwCloseOption*<br/>
Флаг, указывающий, при каких обстоятельствах объекта OLE сохраняется при возвращении в загруженное состояние. Список возможных значений см. в разделе [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close).

### <a name="remarks"></a>Примечания

Уничтожает элемент клиента.

## <a name="see-also"></a>См. также

[Пример MFC MFCBIND](../../overview/visual-cpp-samples.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)
