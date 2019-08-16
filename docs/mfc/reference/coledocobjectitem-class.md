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
ms.openlocfilehash: c6e00bf42cf20b46c949c218efe1820cc7ce0f9b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504008"
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
|[COleDocObjectItem:: COleDocObjectItem](#coledocobjectitem)|`COleDocObject` Конструирует элемент.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[COleDocObjectItem::D Одефаултпринтинг](#dodefaultprinting)|Печать документа приложения контейнера с использованием параметров принтера по умолчанию.|
|[COleDocObjectItem:: Ексеккомманд](#execcommand)|Выполняет команду, указанную пользователем.|
|[COleDocObjectItem:: Жетактивевиев](#getactiveview)|Извлекает активное представление документа.|
|[COleDocObjectItem:: Жетпажекаунт](#getpagecount)|Извлекает количество страниц в документе приложения контейнера.|
|[COleDocObjectItem:: Онпрепарепринтинг](#onprepareprinting)|Подготавливает документ приложения контейнера для печати.|
|[COleDocObjectItem:: OnPrint](#onprint)|Выводит документ приложения контейнера.|
|[COleDocObjectItem:: Куерикомманд](#querycommand)|Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.|
|[COleDocObjectItem:: Release](#release)|Освобождает подключение к связанному элементу OLE и закрывает его, если он был открыт. Не уничтожает клиентский элемент.|

## <a name="remarks"></a>Примечания

В MFC активный документ обрабатывается аналогично обычному встроенному внедрению с возможностью редактирования со следующими отличиями.

- Класс `COleDocument`, производный от, по-прежнему сохраняет список внедренных в данный момент элементов, однако эти `COleDocObjectItem`элементы могут быть производными.

- Если активный документ активен, он занимает всю клиентскую область представления, когда она находится в активном состоянии.

- Активный контейнер документа имеет полный контроль над меню " **Справка** ".

- Меню **Справка** содержит пункты меню для активного контейнера документа и сервера.

Поскольку контейнер активного документа владеет меню " **Справка** ", контейнер отвечает за сообщения меню " **Справка** сервера" на сервер. Эта интеграция обрабатывается `COleDocObjectItem`.

Дополнительные сведения о слиянии меню и активации активных документов см. в разделе Обзор [включения активного документа](../../mfc/active-document-containment.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[кдоЦитем](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`COleDocObjectItem`

## <a name="requirements"></a>Требования

**Заголовок:** афксоле. h

##  <a name="coledocobjectitem"></a>COleDocObjectItem:: COleDocObjectItem

Вызовите эту функцию члена для инициализации `COleDocObjectItem` объекта.

```
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```

### <a name="parameters"></a>Параметры

*пконтаинердок*<br/>
Указатель на `COleDocument` объект, выступающий в качестве активного контейнера документа. Этот параметр должен иметь значение NULL, чтобы включить IMPLEMENT_SERIALIZE. Обычно элементы OLE создаются с указателем документа со значением, отличным от NULL.

##  <a name="dodefaultprinting"></a>COleDocObjectItem::D Одефаултпринтинг

Вызвано платформой в документ с использованием параметров по умолчанию.

```
static HRESULT DoDefaultPrinting(
    CView* pCaller,
    CPrintInfo* pInfo);
```

### <a name="parameters"></a>Параметры

*пкаллер*<br/>
Указатель на объект [CView](../../mfc/reference/cview-class.md) , который отправляет команду Print.

*пинфо*<br/>
Указатель на объект [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) , описывающий задание для печати.

##  <a name="execcommand"></a>COleDocObjectItem:: Ексеккомманд

Вызовите эту функцию члена, чтобы выполнить команду, указанную пользователем.

```
HRESULT ExecCommand(
    DWORD nCmdID,
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,
    const GUID* pguidCmdGroup = NULL);
```

### <a name="parameters"></a>Параметры

*нкмдид*<br/>
Идентификатор выполняемой команды. Должен входить в группу, обозначенную *пгуидкмдграуп*.

*нкмдексекопт*<br/>
Задает параметры выполнения команды. По умолчанию задайте для выполнения команды без запроса пользователя. Список значений см. в разделе [олекмдексекопт](/windows/win32/api/docobj/ne-docobj-olecmdexecopt) .

*пгуидкмдграуп*<br/>
Уникальный идентификатор группы команд. По умолчанию имеет значение NULL, которое указывает стандартную группу. Команда, передаваемая в *нкмдид* , должна принадлежать к группе.

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения возвращает значение S_OK; в противном случае возвращает один из следующих кодов ошибок.

|Значение|Описание|
|-----------|-----------------|
|E_UNEXPECTED|Произошла непредвиденная ошибка.|
|E_FAIL|Произошла ошибка.|
|E_NOTIMPL|Указывает, что библиотека MFC должна попытаться преобразовать и отправить команду.|
|OLECMDERR_E_UNKNOWNGROUP|*пгуидкмдграуп* не имеет значение null, но не указывает распознанную группу команд.|
|OLECMDERR_E_NOTSUPPORTED|*нкмдид* не распознана как допустимая команда в группе пграуп.|
|OLECMDERR_DISABLED|Команда, определенная параметром *нкмдид* , отключена и не может быть выполнена.|
|OLECMDERR_NOHELP|Вызывающая сторона запросила справку по команде, указанной параметром *нкмдид* , но Справка недоступна.|
|OLECMDERR_CANCELLED|Пользователь отменил выполнение.|

### <a name="remarks"></a>Примечания

Параметры *пгуидкмдграуп* и *нкмдид* однозначно идентифицируют вызываемую команду. Параметр *нкмдексекопт* указывает точное выполняемое действие.

##  <a name="getactiveview"></a>COleDocObjectItem:: Жетактивевиев

Вызовите эту функцию-член, чтобы получить указатель `IOleDocumentView` на интерфейс текущего активного представления.

```
LPOLEDOCUMENTVIEW GetActiveView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс [иоледокументвиев](/windows/win32/api/docobj/nn-docobj-ioledocumentview) текущего активного представления. Если текущее представление отсутствует, возвращается значение NULL.

### <a name="remarks"></a>Примечания

Счетчик ссылок на возвращаемый `IOleDocumentView` указатель не увеличивается до тех пор, пока эта функция не вернет значение.

##  <a name="getpagecount"></a>COleDocObjectItem:: Жетпажекаунт

Вызовите эту функцию члена, чтобы получить количество страниц в документе.

```
BOOL GetPageCount(
    LPLONG pnFirstPage,
    LPLONG pcPages);
```

### <a name="parameters"></a>Параметры

*пнфирстпаже*<br/>
Указатель на номер первой страницы документа. Может иметь значение NULL, что означает, что вызывающему объекту не требуется это число.

*пкпажес*<br/>
Указатель на общее число страниц в документе. Может иметь значение NULL, что означает, что вызывающему объекту не требуется это число.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="onprepareprinting"></a>COleDocObjectItem:: Онпрепарепринтинг

Эта функция-член вызывается платформой для подготовки документа к печати.

```
static BOOL OnPreparePrinting(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Параметры

*пкаллер*<br/>
Указатель на объект [CView](../../mfc/reference/cview-class.md) , который отправляет команду Print.

*пинфо*<br/>
Указатель на объект [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) , описывающий задание для печати.

*бпринталл*<br/>
Указывает, следует ли печатать весь документ.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="onprint"></a>COleDocObjectItem:: OnPrint

Эта функция-член вызывается платформой для печати документа.

```
static void OnPrint(
    CView* pCaller,
    CPrintInfo* pInfo,
    BOOL bPrintAll = TRUE);
```

### <a name="parameters"></a>Параметры

*пкаллер*<br/>
Указатель на объект CView, который отправляет команду Print.

*пинфо*<br/>
Указатель на объект [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) , описывающий задание для печати.

*бпринталл*<br/>
Указывает, следует ли печатать весь документ.

##  <a name="querycommand"></a>COleDocObjectItem:: Куерикомманд

Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.

```
HRESULT QueryCommand(
    ULONG nCmdID,
    DWORD* pdwStatus,
    OLECMDTEXT* pCmdText =NULL,
    const GUID* pguidCmdGroup =NULL);
```

### <a name="parameters"></a>Параметры

*нкмдид*<br/>
Идентификатор команды, для которой выполняется запрос.

*пдвстатус*<br/>
Указатель на флаги, возвращаемые в результате запроса. Список возможных значений см. в разделе [OLECMDF](/windows/win32/api/docobj/ne-docobj-olecmdf).

*пкмдтекст*<br/>
Указатель на структуру [олекмдтекст](/windows/win32/api/docobj/ns-docobj-olecmdtext) , в которой возвращаются имя и сведения о состоянии для одной команды. Может иметь значение NULL, чтобы указать, что вызывающему объекту не требуются эти сведения.

*пгуидкмдграуп*<br/>
Уникальный идентификатор группы команд; может иметь значение NULL, чтобы указать стандартную группу.

### <a name="return-value"></a>Возвращаемое значение

Полный список возвращаемых значений см. в разделе [IOleCommandTarget:: QueryStatus](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) в Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция члена эмулирует функциональность метода [IOleCommandTarget:: QueryStatus](/windows/win32/api/docobj/nf-docobj-iolecommandtarget-querystatus) , как описано в Windows SDK.

##  <a name="release"></a>COleDocObjectItem:: Release

Освобождает подключение к связанному элементу OLE и закрывает его, если он был открыт. Не уничтожает клиентский элемент.

```
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```

### <a name="parameters"></a>Параметры

*двклосеоптион*<br/>
Флаг, указывающий, при каких обстоятельствах объект OLE сохраняется при возвращении в состояние загруженности. Список возможных значений см. в разделе [COleClientItem:: Close](../../mfc/reference/coleclientitem-class.md#close).

### <a name="remarks"></a>Примечания

Не уничтожает клиентский элемент.

## <a name="see-also"></a>См. также

[Пример МФКБИНД для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)<br/>
[Класс CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)
