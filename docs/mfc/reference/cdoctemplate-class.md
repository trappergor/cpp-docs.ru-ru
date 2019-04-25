---
title: Класс CDocTemplate
ms.date: 11/04/2016
f1_keywords:
- CDocTemplate
- AFXWIN/CDocTemplate
- AFXWIN/CDocTemplate::CDocTemplate
- AFXWIN/CDocTemplate::AddDocument
- AFXWIN/CDocTemplate::CloseAllDocuments
- AFXWIN/CDocTemplate::CreateNewDocument
- AFXWIN/CDocTemplate::CreateNewFrame
- AFXWIN/CDocTemplate::CreateOleFrame
- AFXWIN/CDocTemplate::CreatePreviewFrame
- AFXWIN/CDocTemplate::GetDocString
- AFXWIN/CDocTemplate::GetFirstDocPosition
- AFXWIN/CDocTemplate::GetNextDoc
- AFXWIN/CDocTemplate::InitialUpdateFrame
- AFXWIN/CDocTemplate::LoadTemplate
- AFXWIN/CDocTemplate::MatchDocType
- AFXWIN/CDocTemplate::OpenDocumentFile
- AFXWIN/CDocTemplate::RemoveDocument
- AFXWIN/CDocTemplate::SaveAllModified
- AFXWIN/CDocTemplate::SetContainerInfo
- AFXWIN/CDocTemplate::SetDefaultTitle
- AFXWIN/CDocTemplate::SetPreviewInfo
- AFXWIN/CDocTemplate::SetServerInfo
helpviewer_keywords:
- CDocTemplate [MFC], CDocTemplate
- CDocTemplate [MFC], AddDocument
- CDocTemplate [MFC], CloseAllDocuments
- CDocTemplate [MFC], CreateNewDocument
- CDocTemplate [MFC], CreateNewFrame
- CDocTemplate [MFC], CreateOleFrame
- CDocTemplate [MFC], CreatePreviewFrame
- CDocTemplate [MFC], GetDocString
- CDocTemplate [MFC], GetFirstDocPosition
- CDocTemplate [MFC], GetNextDoc
- CDocTemplate [MFC], InitialUpdateFrame
- CDocTemplate [MFC], LoadTemplate
- CDocTemplate [MFC], MatchDocType
- CDocTemplate [MFC], OpenDocumentFile
- CDocTemplate [MFC], RemoveDocument
- CDocTemplate [MFC], SaveAllModified
- CDocTemplate [MFC], SetContainerInfo
- CDocTemplate [MFC], SetDefaultTitle
- CDocTemplate [MFC], SetPreviewInfo
- CDocTemplate [MFC], SetServerInfo
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
ms.openlocfilehash: 3b2d84af9be8e5c606cde8794b51e12207dcdec9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62163991"
---
# <a name="cdoctemplate-class"></a>Класс CDocTemplate

Абстрактный базовый класс, который определяет базовую функциональность шаблонов документов.

## <a name="syntax"></a>Синтаксис

```
class CDocTemplate : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|name|Описание|
|----------|-----------------|
|[CDocTemplate::CDocTemplate](#cdoctemplate)|Создает объект `CDocTemplate`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CDocTemplate::AddDocument](#adddocument)|Добавляет документ в шаблон.|
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|Закрывает все документы, связанные с этим шаблоном.|
|[CDocTemplate::CreateNewDocument](#createnewdocument)|Создает новый документ.|
|[CDocTemplate::CreateNewFrame](#createnewframe)|Создает новое окно фрейма, содержащее документ и представление.|
|[CDocTemplate::CreateOleFrame](#createoleframe)|Создает окно фрейма поддержкой OLE.|
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Создает дочерний кадр, используемый для расширенного просмотра.|
|[CDocTemplate::GetDocString](#getdocstring)|Извлекает строку, связанную с типом документа.|
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Возвращает позицию первого документа, связанного с этим шаблоном.|
|[CDocTemplate::GetNextDoc](#getnextdoc)|Получает документ и положение следующего.|
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Инициализирует фрейм окна и при необходимости делает его видимым.|
|[CDocTemplate::LoadTemplate](#loadtemplate)|Загружает ресурсы для данного `CDocTemplate` или производного класса.|
|[CDocTemplate::MatchDocType](#matchdoctype)|Определяет степень уверенности в соответствие между типом документа и этот шаблон.|
|[Функции](#opendocumentfile)|Открывает файл, указанный параметром pathname.|
|[CDocTemplate::RemoveDocument](#removedocument)|Удаление документа из шаблона.|
|[CDocTemplate::SaveAllModified](#saveallmodified)|Сохраняет все документы, связанные с помощью этого шаблона, которые были изменены.|
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|Определяет ресурсы для контейнеров OLE, при редактировании объекта OLE на месте.|
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|Отображает заголовок по умолчанию в строке заголовка окна документа.|
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|Настройки вне процесса Предварительный просмотр обработчика.|
|[CDocTemplate::SetServerInfo](#setserverinfo)|Определяет ресурсы и классы, когда серверный документ внедряется или редактируется по месту.|

## <a name="remarks"></a>Примечания

Обычно создается один или несколько шаблонов документов в реализации приложения `InitInstance` функции. Шаблон документа определяет отношения между три типа классов:

- Класс документа, который вы наследуете от `CDocument`.

- Класс представления, который отображает данные из класса документа, перечисленных выше. Можно наследовать этот класс из `CView`, `CScrollView`, `CFormView`, или `CEditView`. (Можно также использовать `CEditView` напрямую.)

- Класс окна фрейма, который содержит представление. Для одного документа интерфейс (SDI) приложения, вам этот класс является производным от `CFrameWnd`. Для нескольких приложений интерфейса (MDI) документа, то этот класс является производным от `CMDIChildWnd`. Если вам не нужно настраивать поведение окна фрейма, можно использовать `CFrameWnd` или `CMDIChildWnd` напрямую без создания собственного производного класса.

Ваше приложение имеет один шаблон документа для каждого типа документа, который он поддерживает. Например если приложение поддерживает электронных таблиц и текстовых документов, приложение имеет два объекта шаблона документа. Каждый шаблон документа несет ответственность за создание и управление ими все документы его типа.

Шаблон документа содержит указатели на `CRuntimeClass` объектов для документов, представления и классы окна фрейма. Эти `CRuntimeClass` объекты указываются при создании шаблона документа.

Шаблон документа содержит идентификатор ресурсы, используемые с типом документа (например, меню, значок или ресурсами таблиц сочетаний клавиш). Шаблон документа также содержит строки, содержащие дополнительные сведения о его тип документа. К ним относятся имя типа документа (например, «лист») и расширение файла (например, «.xls»). При необходимости он может содержать другие строки, используется пользовательский интерфейс приложения, диспетчер файлов Windows и связывания объектов и поддержка внедрения (OLE).

Если приложение является OLE-контейнер и/или сервер, шаблон документа также определяет идентификатор меню, использованного при активации на месте. Если приложение является OLE-сервер, шаблон документа определяет идентификатор панели инструментов и меню, которое используется во время активации на месте. Укажите следующие дополнительные ресурсы OLE, вызвав `SetContainerInfo` и `SetServerInfo`.

Поскольку `CDocTemplate` является абстрактным классом, класс нельзя использовать напрямую. Типичное приложение использует один из двух `CDocTemplate`-производные классы, предоставляемый библиотекой классов Microsoft Foundation: `CSingleDocTemplate`, который реализует SDI, и `CMultiDocTemplate`, который реализует MDI. См. в статье эти классы, Дополнительные сведения об использовании шаблонов документов.

Если приложению требуется парадигма пользовательского интерфейса, которая существенно отличается от SDI или MDI, вы можете собственный производный класс из `CDocTemplate`.

Дополнительные сведения о `CDocTemplate`, см. в разделе [шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocTemplate`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="adddocument"></a>  CDocTemplate::AddDocument

Эту функцию можно используйте для добавления документа в шаблон.

```
virtual void AddDocument(CDocument* pDoc);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указатель должен быть добавлен в документ.

### <a name="remarks"></a>Примечания

Производные классы [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) и [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) переопределите эту функцию. При наследовании класса шаблонов документов из `CDocTemplate`, эту функцию необходимо переопределить в производном классе.

##  <a name="cdoctemplate"></a>  CDocTemplate::CDocTemplate

Создает объект `CDocTemplate`.

```
CDocTemplate (
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Параметры

*nIDResource*<br/>
Указывает идентификатор ресурсы, используемые с типом документа. Это может включать меню, значок, таблицу сочетаний клавиш и строковые ресурсы.

Строковый ресурс состоит из до семи подстрок, разделенных символом '\n' ('\n' символ необходим в качестве заполнителя, если подстрока не включается; тем не менее, конечные символы '\n' не требуются); Эти подстроки описания типа документа. Сведения о подстроках, см. в разделе [GetDocString](#getdocstring). Этот строковый ресурс находится в файле ресурсов приложения. Пример:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Обратите внимание, что строка начинается со знака «\n»; Это обусловлено первую подстроку не используется в приложениях MDI и поэтому не включается. Можно изменить эту строку, с помощью редактора; вся строка представляется как одна запись в редакторе строку не семь отдельных записей.

*pDocClass*<br/>
Указывает на `CRuntimeClass` объектом класса документа. Этот класс является `CDocument`-производный класс, определенный для представления документов.

*pFrameClass*<br/>
Указывает на `CRuntimeClass` объект класс окна фрейма. Этот класс может быть `CFrameWnd`-производного класса, или он может быть `CFrameWnd` сам, если требуется поведение по умолчанию для окна главного фрейма.

*pViewClass*<br/>
Указывает на `CRuntimeClass` объекта класса представления. Этот класс является `CView`-производный класс, определенный для отображения документов.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член для создания `CDocTemplate` объекта. Динамически выделять `CDocTemplate` объект и передать его в [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) из `InitInstance` функцию-член класса приложения.

##  <a name="closealldocuments"></a>  CDocTemplate::CloseAllDocuments

Вызывайте эту функцию члена, чтобы закрыть все открытые документы.

```
virtual void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Параметры

*bEndSession*<br/>
Не используется.

### <a name="remarks"></a>Примечания

Эта функция-член обычно используется как часть команды файл: выход. Реализация по умолчанию эта функция вызывает [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) функция-член удалять документа данные и затем закрывает окна фрейма для всех представлений, присоединенные к документу.

Переопределите эту функцию, если требуется запрашивать у пользователя для выполнения специальных операций очистки обработки перед закрытием документа. Например если документ представляет запись в базу данных, может потребоваться переопределить эту функцию, чтобы закрыть базу данных.

##  <a name="createnewdocument"></a>  CDocTemplate::CreateNewDocument

Вызывайте эту функцию члена, чтобы создать новый документ, тип которого связан с помощью этого шаблона документа.

```
virtual CDocument* CreateNewDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданного документа или значение NULL, если произошла ошибка.

##  <a name="createnewframe"></a>  CDocTemplate::CreateNewFrame

Создает новое окно фрейма, содержащее документ и представление.

```
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,
    CFrameWnd* pOther);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Документ, к которому должен ссылаться нового окна области. Может иметь значение NULL.

*pOther*<br/>
Окна фрейма, на которой будет основываться нового окна области. Может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданный объект окна, или значение NULL, если возникает ошибка.

### <a name="remarks"></a>Примечания

`CreateNewFrame` использует `CRuntimeClass` объекты передаются в конструктор, чтобы создать новый объект окна представление и вложенный документ. Если *pDoc* параметра равно NULL, платформа выводится сообщение ТРАССИРОВКИ.

*POther* параметр используется для реализации окно новой команды. Он предоставляет окно рамки, выступающей в качестве модели нового окна области. Обычно создается невидимым нового окна области. Вызывайте эту функцию для создания окна фрейма за пределами Стандартная реализация структуры Создание и открытие файла.

##  <a name="createoleframe"></a>  CDocTemplate::CreateOleFrame

Создает окно фрейма OLE.

```
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,
    CDocument* pDoc,
    BOOL bCreateView);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительское окно фрейма.

*pDoc*<br/>
Указатель на документ, к которому должен ссылаться нового окна области OLE.

*bCreateView*<br/>
Определяет, создается ли представления вместе с кадр.

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Если *bCreateView* равно нулю, создается пустая рамка.

##  <a name="getdocstring"></a>  CDocTemplate::GetDocString

Извлекает строку, связанную с типом документа.

```
virtual BOOL GetDocString(
    CString& rString,
    enum DocStringIndex index) const;
```

### <a name="parameters"></a>Параметры

*rString*<br/>
Ссылку на `CString` объект, который будет содержать строку, когда функция возвращает.

*Индекс*<br/>
Индекс подстроки, извлекаемых из строку, которая описывает тип документа. Этот параметр может принимать одно из следующих значений:

- `CDocTemplate::windowTitle` Имя, отображаемое в строке (например, «Microsoft Excel») заголовка окна приложения. Представление только в шаблоне документа для приложения SDI.

- `CDocTemplate::docName` Корневой каталог для имя документа по умолчанию (например, «Лист»). Этого корня, а также ряд, используется имя по умолчанию новый документ этого типа всякий раз, когда пользователь выбирает новую команду меню "файл" (например, «Лист1» или «Лист2»). Если не указан, «Без имени» используется по умолчанию.

- `CDocTemplate::fileNewName` Имя этого типа документа. Если приложение поддерживает более чем один тип документа, эта строка отображается в диалоговом окне новый файл (например, «лист»). Если не указано, что документ имеет тип недоступен, с помощью команды создания файла.

- `CDocTemplate::filterName` Описание типа документа и фильтр с подстановочными знаками соответствующих документов этого типа. Эта строка отображается в раскрывающемся списке Тип файлов в диалоговом окне открытия файла (например, «рабочие (*.xls)»). Если не указано, что документ имеет тип недоступен, с помощью команды открытия файла.

- `CDocTemplate::filterExt` Расширение для документов этого типа (например, «.xls»). Если не указано, что документ имеет тип недоступен, с помощью команды открытия файла.

- `CDocTemplate::regFileTypeId` Идентификатор типа документа должен храниться в базе данных регистрации, поддерживаемых Windows. Эта строка представляет собой только для внутреннего использования (например, «ExcelWorksheet»). Если не указан, тип документа не регистрируются с помощью диспетчера файлов Windows.

- `CDocTemplate::regFileTypeName` Имя типа документа, для сохранения в базе данных регистрации. Эта строка может отображаться в диалоговых окнах приложений, которые обращаются к базе данных регистрации (например, «лист Microsoft Excel»).

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если найден заданной подстроки; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для получения конкретной подстроки, описывающий тип документа. Строка, содержащая эти подстроки хранится в шаблоне документа, а также является производным из строки в файле ресурсов для приложения. Платформа вызывает эту функцию для получения строк, которые необходимы для пользовательского интерфейса приложения. Если вы указали с расширением имени файла для документов вашего приложения, платформа также вызывает эту функцию, при добавлении записи в базе данных регистрации Windows; Это позволяет открывать диспетчер файлов Windows документы.

Вызывайте эту функцию только в том случае, если при наследовании класса из `CDocTemplate`.

##  <a name="getfirstdocposition"></a>  CDocTemplate::GetFirstDocPosition

Возвращает позицию первого документа, связанного с этим шаблоном.

```
virtual POSITION GetFirstDocPosition() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, который может использоваться для итерации по списку документов, связанных с помощью этого шаблона документа; или значение NULL, если список пуст.

### <a name="remarks"></a>Примечания

Эту функцию можно используйте для получения позиции первого документа в список документов, связанный с этим шаблоном. Использовать значение ПОЗИЦИИ в качестве аргумента для [CDocTemplate::GetNextDoc](#getnextdoc) для выполнения итерации по списку документов, связанных с шаблоном.

[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) и [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) переопределяется это чистой виртуальной функции. Любого класса, производного от `CDocTemplate` необходимо также переопределить эту функцию.

##  <a name="getnextdoc"></a>  CDocTemplate::GetNextDoc

Извлекает список элементом, определяемым *значений RPO*, затем задает *важности* значению ПОЗИЦИИ на следующую запись в списке.

```
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий документ в список документов, связанный с этим шаблоном.

### <a name="parameters"></a>Параметры

*важности*<br/>
Ссылку на ПОЗИЦИЮ, возвращенное предыдущим вызовом [GetFirstDocPosition](#getfirstdocposition) или `GetNextDoc`.

### <a name="remarks"></a>Примечания

Если полученного элемента является последним в списке, то новое значение *важности* имеет значение NULL.

Можно использовать `GetNextDoc` в цикле прямой итерации, если установить начальное положение, с помощью вызова [GetFirstDocPosition](#getfirstdocposition).

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

##  <a name="initialupdateframe"></a>  CDocTemplate::InitialUpdateFrame

Инициализирует фрейм окна и при необходимости делает его видимым.

```
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,
    CDocument* pDoc,
    BOOL bMakeVisible = TRUE);
```

### <a name="parameters"></a>Параметры

*pFrame*<br/>
Окна фрейма, которому требуется обновление.

*pDoc*<br/>
Документ, с которым связан кадр. Может иметь значение NULL.

*bMakeVisible*<br/>
Указывает ли кадр должен стать видимым и активных.

### <a name="remarks"></a>Примечания

Вызовите `IntitialUpdateFrame` после создания новый кадр с `CreateNewFrame`. Вызов этой функции приводит к представлениям в этом окне фрейма для получения их `OnInitialUpdate` вызовов. Кроме того Если не ранее активное представление, первичное представление окна фрейма делается активным; Первичное представление — это представление с дочерним идентификатор из AFX_IDW_PANE_FIRST. Наконец, является видимым окно фрейма Если *bMakeVisible* имеет ненулевое значение. Если *bMakeVisible* равен нулю, текущего фокуса, и режим отображения окна фрейма, останутся без изменений.

Вызывайте эту функцию, при использовании реализации платформы новый файл и открытие файла необязателен.

##  <a name="loadtemplate"></a>  CDocTemplate::LoadTemplate

Загружает ресурсы для данного `CDocTemplate` или производного класса.

```
virtual void LoadTemplate();
```

### <a name="remarks"></a>Примечания

Эта функция-член вызывается платформой для загрузки ресурсов для заданного `CDocTemplate` или производного класса. Обычно он вызывается во время построения, за исключением при шаблона создается глобально. В этом случае вызов `LoadTemplate` откладывается до [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) вызывается.

##  <a name="matchdoctype"></a>  CDocTemplate::MatchDocType

Определяет степень уверенности в соответствие между типом документа и этот шаблон.

```
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,
    CDocument*& rpDocMatch);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Путь файла, тип которого требуется определить.

*rpDocMatch*<br/>
Указатель на документ, который назначается документу с совпадением, если файл, заданный параметром *lpszPathName* уже открыт.

### <a name="return-value"></a>Возвращаемое значение

Значение из **достоверности** перечисления, который определяется следующим образом:

```
enum Confidence
    {
    noAttempt,
    maybeAttemptForeign,
    maybeAttemptNative,
    yesAttemptForeign,
    yesAttemptNative,
    yesAlreadyOpen
    };
```

### <a name="remarks"></a>Примечания

Эта функция используется для определения типа документа шаблона, используемого для открытия файла. Если приложение поддерживает несколько типов файлов, например, вы эта функция используется, чтобы определить, какой из шаблонов документов, доступных для данного файла, вызвав `MatchDocType` для каждого шаблона, в свою очередь и выбрав шаблон в соответствии с Возвращаемое значение достоверности.

Если файл, заданный параметром *lpszPathName* уже открыт, эта функция возвращает `CDocTemplate::yesAlreadyOpen` и копирует его `CDocument` объект в объект, находящийся в *rpDocMatch*.

Если файл не открыт, но с расширением в *lpszPathName* совпадает с расширением, заданным по `CDocTemplate::filterExt`, эта функция возвращает `CDocTemplate::yesAttemptNative` и задает *rpDocMatch* значение NULL. Дополнительные сведения о `CDocTemplate::filterExt`, см. в разделе [CDocTemplate::GetDocString](#getdocstring).

Если ни одна из регистр имеет значение true, функция возвращает `CDocTemplate::yesAttemptForeign`.

Реализация по умолчанию не возвращает `CDocTemplate::maybeAttemptForeign` или `CDocTemplate::maybeAttemptNative`. Переопределите эту функцию для реализации логики сопоставление типов подходящее для используемого приложения, возможно с помощью этих двух значений из **достоверности** перечисления.

##  <a name="opendocumentfile"></a>  Функции

Открывает файл, указанный путь.

```
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;

virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU) = 0;
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
[in] Указатель на путь к файлу, содержащему открываемого документа.

*bAddToMRU*<br/>
[in] Значение TRUE указывает, что документ является одним из последних файлов; Значение FALSE указывает, что документ не является ни один из последних файлов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на документ, именем которого файл *lpszPathName*; Имеет значение NULL, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Открывает файл, путь которого задается *lpszPathName*. Если *lpszPathName* имеет значение NULL, создается новый файл, который содержит документ, тип которого связан с помощью этого шаблона.

##  <a name="removedocument"></a>  CDocTemplate::RemoveDocument

Удаляет документа, на которые указывают *pDoc* из списка документов, связанных с этим шаблоном.

```
virtual void RemoveDocument(CDocument* pDoc);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указатель на документ, для удаления.

### <a name="remarks"></a>Примечания

Производные классы `CMultiDocTemplate` и `CSingleDocTemplate` переопределите эту функцию. При наследовании класса шаблонов документов из `CDocTemplate`, эту функцию необходимо переопределить в производном классе.

##  <a name="saveallmodified"></a>  CDocTemplate::SaveAllModified

Сохранение всех документов, которые были изменены.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; в противном случае 0.

##  <a name="setcontainerinfo"></a>  CDocTemplate::SetContainerInfo

Определяет ресурсы для контейнеров OLE, при редактировании объекта OLE на месте.

```
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```

### <a name="parameters"></a>Параметры

*nIDOleInPlaceContainer*<br/>
Идентификатор ресурсы, используемые при активации внедренный объект.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы задать ресурсы, которые будут использоваться, когда объект OLE активироваться на месте. Эти ресурсы могут включать меню и таблицы сочетаний клавиш. Эта функция обычно вызывается [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) функции приложения.

Меню, связанное с *nIDOleInPlaceContainer* содержит разделители, которые позволяют меню активированного элемента на месте выполнить слияние с меню контейнера приложений. Дополнительные сведения об объединении меню "server" и контейнера, см. в статье [меню и ресурсы (OLE)](../../mfc/menus-and-resources-ole.md).

##  <a name="setdefaulttitle"></a>  CDocTemplate::SetDefaultTitle

Вызывайте эту функцию для загрузки по умолчанию заголовок документа и отображения в строке заголовка документа.

```
virtual void SetDefaultTitle(CDocument* pDocument) = 0;
```

### <a name="parameters"></a>Параметры

*pDocument*<br/>
Указатель на документ, чья должность имеет устанавливаемое значение.

### <a name="remarks"></a>Примечания

Сведения о заголовок по умолчанию, см. в описании `CDocTemplate::docName` в [CDocTemplate::GetDocString](#getdocstring).

##  <a name="setserverinfo"></a>  CDocTemplate::SetServerInfo

Определяет ресурсы и классы, когда серверный документ внедряется или редактируется по месту.

```
void SetServerInfo(
    UINT nIDOleEmbedding,
    UINT nIDOleInPlaceServer = 0,
    CRuntimeClass* pOleFrameClass = NULL,
    CRuntimeClass* pOleViewClass = NULL);
```

### <a name="parameters"></a>Параметры

*nIDOleEmbedding*<br/>
Идентификатор ресурсы, используемые при открытии связанного объекта в отдельном окне.

*nIDOleInPlaceServer*<br/>
Идентификатор ресурсы, используемые при внедренный объект активации на месте.

*pOleFrameClass*<br/>
Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структура, содержащая сведения о классе для объекта окна фрейма, созданного при активации на месте.

*pOleViewClass*<br/>
Указатель на `CRuntimeClass` структура, содержащая сведения о классе для представления объекта, созданного при активации на месте.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член для идентификации ресурсов, которые будут использоваться серверным приложением, когда пользователь запрашивает активации внедренный объект. Эти ресурсы состоят из меню и таблицы сочетаний клавиш. Эта функция обычно вызывается `InitInstance` приложения.

Меню, связанное с *nIDOleInPlaceServer* содержит разделители, которые позволяют меню сервер выполнить слияние с меню контейнера. Дополнительные сведения об объединении меню "server" и контейнера, см. в статье [меню и ресурсы (OLE)](../../mfc/menus-and-resources-ole.md).

##  <a name="createpreviewframe"></a>  CDocTemplate::CreatePreviewFrame

Создает дочерний кадр, используемый для расширенного просмотра.

```
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,
    CDocument* pDoc);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на родительское окно (обычно заданного оболочкой).

*pDoc*<br/>
Указатель на объект документа, содержимое которых будет просматриваться.

### <a name="return-value"></a>Возвращаемое значение

Допустимый указатель на `CFrameWnd` объект или значение NULL, если создание завершается сбоем.

### <a name="remarks"></a>Примечания

##  <a name="setpreviewinfo"></a>  CDocTemplate::SetPreviewInfo

Устанавливает ожидания процесса обработчика просмотра.

```
void SetPreviewInfo(
    UINT nIDPreviewFrame,
    CRuntimeClass* pPreviewFrameClass = NULL,
    CRuntimeClass* pPreviewViewClass = NULL);
```

### <a name="parameters"></a>Параметры

*nIDPreviewFrame*<br/>
Указывает идентификатор ресурса рамки предварительной версии.

*pPreviewFrameClass*<br/>
Задает указатель на структуру сведения класса среды выполнения рамки предварительной версии.

*pPreviewViewClass*<br/>
Задает указатель на структуру сведений класса среды выполнения Предварительный просмотр.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)<br/>
[Класс CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[Класс CDocument](../../mfc/reference/cdocument-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CScrollView](../../mfc/reference/cscrollview-class.md)<br/>
[Класс CEditView](../../mfc/reference/ceditview-class.md)<br/>
[Класс CFormView](../../mfc/reference/cformview-class.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)
