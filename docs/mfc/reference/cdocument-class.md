---
title: Класс CDocument
ms.date: 11/04/2016
f1_keywords:
- CDocument
- AFXWIN/CDocument
- AFXWIN/CDocument::CDocument
- AFXWIN/CDocument::AddView
- AFXWIN/CDocument::BeginReadChunks
- AFXWIN/CDocument::CanCloseFrame
- AFXWIN/CDocument::ClearChunkList
- AFXWIN/CDocument::ClearPathName
- AFXWIN/CDocument::DeleteContents
- AFXWIN/CDocument::FindChunk
- AFXWIN/CDocument::GetAdapter
- AFXWIN/CDocument::GetDocTemplate
- AFXWIN/CDocument::GetFile
- AFXWIN/CDocument::GetFirstViewPosition
- AFXWIN/CDocument::GetNextView
- AFXWIN/CDocument::GetPathName
- AFXWIN/CDocument::GetThumbnail
- AFXWIN/CDocument::GetTitle
- AFXWIN/CDocument::InitializeSearchContent
- AFXWIN/CDocument::IsModified
- AFXWIN/CDocument::IsSearchAndOrganizeHandler
- AFXWIN/CDocument::LoadDocumentFromStream
- AFXWIN/CDocument::OnBeforeRichPreviewFontChanged
- AFXWIN/CDocument::OnChangedViewList
- AFXWIN/CDocument::OnCloseDocument
- AFXWIN/CDocument::OnCreatePreviewFrame
- AFXWIN/CDocument::OnDocumentEvent
- AFXWIN/CDocument::OnDrawThumbnail
- AFXWIN/CDocument::OnLoadDocumentFromStream
- AFXWIN/CDocument::OnNewDocument
- AFXWIN/CDocument::OnOpenDocument
- AFXWIN/CDocument::OnPreviewHandlerQueryFocus
- AFXWIN/CDocument::OnPreviewHandlerTranslateAccelerator
- AFXWIN/CDocument::OnRichPreviewBackColorChanged
- AFXWIN/CDocument::OnRichPreviewFontChanged
- AFXWIN/CDocument::OnRichPreviewSiteChanged
- AFXWIN/CDocument::OnRichPreviewTextColorChanged
- AFXWIN/CDocument::OnSaveDocument
- AFXWIN/CDocument::OnUnloadHandler
- AFXWIN/CDocument::PreCloseFrame
- AFXWIN/CDocument::ReadNextChunkValue
- AFXWIN/CDocument::ReleaseFile
- AFXWIN/CDocument::RemoveChunk
- AFXWIN/CDocument::RemoveView
- AFXWIN/CDocument::ReportSaveLoadException
- AFXWIN/CDocument::SaveModified
- AFXWIN/CDocument::SetChunkValue
- AFXWIN/CDocument::SetModifiedFlag
- AFXWIN/CDocument::SetPathName
- AFXWIN/CDocument::SetTitle
- AFXWIN/CDocument::UpdateAllViews
- AFXWIN/CDocument::OnFileSendMail
- AFXWIN/CDocument::OnUpdateFileSendMail
- AFXWIN/CDocument::m_bGetThumbnailMode
- AFXWIN/CDocument::m_bPreviewHandlerMode
- AFXWIN/CDocument::m_bSearchMode
- AFXWIN/CDocument::m_clrRichPreviewBackColor
- AFXWIN/CDocument::m_clrRichPreviewTextColor
- AFXWIN/CDocument::m_lfRichPreviewFont
helpviewer_keywords:
- CDocument [MFC], CDocument
- CDocument [MFC], AddView
- CDocument [MFC], BeginReadChunks
- CDocument [MFC], CanCloseFrame
- CDocument [MFC], ClearChunkList
- CDocument [MFC], ClearPathName
- CDocument [MFC], DeleteContents
- CDocument [MFC], FindChunk
- CDocument [MFC], GetAdapter
- CDocument [MFC], GetDocTemplate
- CDocument [MFC], GetFile
- CDocument [MFC], GetFirstViewPosition
- CDocument [MFC], GetNextView
- CDocument [MFC], GetPathName
- CDocument [MFC], GetThumbnail
- CDocument [MFC], GetTitle
- CDocument [MFC], InitializeSearchContent
- CDocument [MFC], IsModified
- CDocument [MFC], IsSearchAndOrganizeHandler
- CDocument [MFC], LoadDocumentFromStream
- CDocument [MFC], OnBeforeRichPreviewFontChanged
- CDocument [MFC], OnChangedViewList
- CDocument [MFC], OnCloseDocument
- CDocument [MFC], OnCreatePreviewFrame
- CDocument [MFC], OnDocumentEvent
- CDocument [MFC], OnDrawThumbnail
- CDocument [MFC], OnLoadDocumentFromStream
- CDocument [MFC], OnNewDocument
- CDocument [MFC], OnOpenDocument
- CDocument [MFC], OnPreviewHandlerQueryFocus
- CDocument [MFC], OnPreviewHandlerTranslateAccelerator
- CDocument [MFC], OnRichPreviewBackColorChanged
- CDocument [MFC], OnRichPreviewFontChanged
- CDocument [MFC], OnRichPreviewSiteChanged
- CDocument [MFC], OnRichPreviewTextColorChanged
- CDocument [MFC], OnSaveDocument
- CDocument [MFC], OnUnloadHandler
- CDocument [MFC], PreCloseFrame
- CDocument [MFC], ReadNextChunkValue
- CDocument [MFC], ReleaseFile
- CDocument [MFC], RemoveChunk
- CDocument [MFC], RemoveView
- CDocument [MFC], ReportSaveLoadException
- CDocument [MFC], SaveModified
- CDocument [MFC], SetChunkValue
- CDocument [MFC], SetModifiedFlag
- CDocument [MFC], SetPathName
- CDocument [MFC], SetTitle
- CDocument [MFC], UpdateAllViews
- CDocument [MFC], OnFileSendMail
- CDocument [MFC], OnUpdateFileSendMail
- CDocument [MFC], m_bGetThumbnailMode
- CDocument [MFC], m_bPreviewHandlerMode
- CDocument [MFC], m_bSearchMode
- CDocument [MFC], m_clrRichPreviewBackColor
- CDocument [MFC], m_clrRichPreviewTextColor
- CDocument [MFC], m_lfRichPreviewFont
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
ms.openlocfilehash: b7358c2206c15660b9ffb283802283ee71e57f03
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299079"
---
# <a name="cdocument-class"></a>Класс CDocument

Предоставляет базовую функциональность для определяемых пользователем классов документа.

## <a name="syntax"></a>Синтаксис

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CDocument::CDocument](#cdocument)|Создает объект `CDocument`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CDocument::AddView](#addview)|Присоединяет представление документа.|
|[CDocument::BeginReadChunks](#beginreadchunks)|Инициализирует Фрагментирование чтения.|
|[CDocument::CanCloseFrame](#cancloseframe)|Advanced переопределяемый; Вызывается перед закрытием окна фрейма, просмотр этого документа.|
|[CDocument::ClearChunkList](#clearchunklist)|Очищает список блоков.|
|[CDocument::ClearPathName](#clearpathname)|Очищает путь объекта документа.|
|[CDocument::DeleteContents](#deletecontents)|Вызывается, чтобы выполнить очистку документа.|
|[CDocument::FindChunk](#findchunk)|Ищет фрагмент данных с указанным идентификатором GUID.|
|[CDocument::GetAdapter](#getadapter)|Возвращает указатель на объект, реализующий интерфейс `IDocument` интерфейс.|
|[CDocument::GetDocTemplate](#getdoctemplate)|Возвращает указатель на шаблон документа, который описывает тип документа.|
|[CDocument::GetFile](#getfile)|Возвращает указатель на нужный `CFile` объекта.|
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|Возвращает позицию первой в списке представлений; используется для начала итерации.|
|[CDocument::GetNextView](#getnextview)|Выполняет итерацию по списку доступных представлений, связанных с документом.|
|[CDocument::GetPathName](#getpathname)|Возвращает путь к файлу данных документа.|
|[CDocument::GetThumbnail](#getthumbnail)|Вызывается для создания растрового изображения для использования поставщика уменьшенных изображений для отображения эскиза.|
|[CDocument::GetTitle](#gettitle)|Возвращает заголовок документа.|
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Вызывается для инициализации содержимого поиска для поиска обработчика.|
|[CDocument::IsModified](#ismodified)|Указывает, является ли документ был изменен с момента последнего сохранения.|
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Сообщает ли этот экземпляр `CDocument` объект был создан для поиска и организовать обработчика.|
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Вызывается, чтобы загрузить данные документа из потока.|
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Вызывается перед изменением расширенного просмотра шрифта.|
|[CDocument::OnChangedViewList](#onchangedviewlist)|Вызывается после представления добавлении или удалении из документа.|
|[CDocument::OnCloseDocument](#onclosedocument)|Вызывается, чтобы закрыть документ.|
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Вызвано структурой при необходимости создать кадр предварительной версии для расширенного просмотра.|
|[CDocument::OnDocumentEvent](#ondocumentevent)|Вызвано структурой в ответ на событие документа.|
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|Переопределите этот метод в производном классе для рисования содержание эскиз.|
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|Вызывается платформой, когда это необходимо загрузить данные документа из потока.|
|[CDocument::OnNewDocument](#onnewdocument)|Вызывается для создания нового документа.|
|[CDocument::OnOpenDocument](#onopendocument)|Вызывается для открытия существующего документа.|
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|Направляет обработчик просмотра для возврата HWND из вызова функции getFocus библиотеки.|
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Направляет обработчик просмотра для обработки нажатия клавиш, передаются из средства переноса сообщений процесс, в которой выполняется обработчик просмотра.|
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Вызывается при изменении цвета фона расширенного просмотра.|
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|Вызывается при изменении шрифта расширенного просмотра.|
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|Вызывается при изменении расширенного просмотра сайта.|
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Вызывается при изменении цвета текста расширенного просмотра.|
|[CDocument::OnSaveDocument](#onsavedocument)|Вызывается, чтобы сохранить документ на диске.|
|[CDocument::OnUnloadHandler](#onunloadhandler)|Вызывается платформой, когда выгружается обработчика просмотра.|
|[CDocument::PreCloseFrame](#precloseframe)|Вызывается перед закрытием окна фрейма.|
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Считывает следующее значение фрагмента данных.|
|[CDocument::ReleaseFile](#releasefile)|Освобождает файл, чтобы сделать его доступным для использования другими приложениями.|
|[CDocument::RemoveChunk](#removechunk)|Удаляет фрагмент данных с указанным идентификатором GUID.|
|[CDocument::RemoveView](#removeview)|Отсоединяет представления из документа.|
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Advanced переопределяемый; вызывается, когда открытый или операция сохранения не может быть завершена из-за исключения.|
|[CDocument::SaveModified](#savemodified)|Advanced переопределяемый; вызывается, чтобы запрашивать у пользователя, следует ли сохранить документ.|
|[CDocument::SetChunkValue](#setchunkvalue)|Задает значение фрагмента данных.|
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Задает флаг, указывающий, что документа были изменены с момента последнего сохранения.|
|[CDocument::SetPathName](#setpathname)|Задает путь к файлу данных, используемые в документе.|
|[CDocument::SetTitle](#settitle)|Задает название документа.|
|[CDocument::UpdateAllViews](#updateallviews)|Уведомляет все представления, в которых описываются был изменен.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[CDocument::OnFileSendMail](#onfilesendmail)|Отправляет сообщение электронной почты с вложенным документом.|
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|Включает команду Отправить почту, если присутствует поддержка электронной почты.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Указывает, что `CDocument` объект был создан при dllhost для эскизов. Должен быть установлен в `CView::OnDraw`.|
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Указывает, что `CDocument` объект был создан при prevhost для `Rich Preview`. Должен быть установлен в `CView::OnDraw`.|
|[CDocument::m_bSearchMode](#m_bsearchmode)|Указывает, что `CDocument` , индексатора или другого приложения поиска создан объект.|
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Задает цвет фона окна расширенного просмотра. Этот цвет задан узлом.|
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Задает основной цвет окна расширенного просмотра. Этот цвет задан узлом.|
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Задает шрифт текста для расширенного просмотра окна. Эти сведения шрифта задается узлом.|

## <a name="remarks"></a>Примечания

Представляет единицу данных, которое пользователь обычно открывается с помощью команды открытия файла и сохраняет с помощью команды сохранения файла.

`CDocument` поддерживает стандартные операции, такие как создание документа, их загрузки и сохранения. Платформа управляет документов с помощью интерфейса, определенного `CDocument`.

Приложение может поддерживать более чем один тип документа; Например приложение может поддерживать электронных таблиц и текстовых документов. Каждый тип документа имеет шаблон связанный документ; шаблон документа определяет, какие ресурсы (например, таблица значок, сочетания клавиш или меню), используемые для этого типа документа. Каждый документ содержит указатель на связанный с ним `CDocTemplate` объекта.

Пользователи взаимодействуют с документа с помощью [CView](../../mfc/reference/cview-class.md) объекты, связанные с ней. Представление отображает изображение в окне фрейма документа и интерпретирует ввод данных пользователем как операций над документом. Документ может иметь несколько представлений, связанных с ним. Когда пользователь открывает окно в документе, платформа создает представление и присоединяет его к документу. Шаблон документа указывает, какой тип представлений и фреймов окна используются для отображения каждого из типов документов.

Документы являются частью стандарта framework команду маршрутизации и поэтому получают команды из компонентов стандартного пользовательского интерфейса (например, элемент меню сохранения файла). Документ получает команды, пересылаемый активное представление. Если документ не обрабатывает определенной команды, он перенаправляет команду, чтобы шаблон документа, который управляет им.

При изменении данных документа, каждый из его представлений должны отражать эти изменения. `CDocument` предоставляет [UpdateAllViews](#updateallviews) функция-член для вас для уведомления представления о таких изменениях, поэтому представлений можно менять представление при необходимости. Платформа также предлагает пользователю сохранить измененный файл перед его закрытием.

Для реализации документов в типичном приложении, выполните следующие действия.

- Наследуйте класс от `CDocument` для каждого типа документа.

- Добавьте переменные-члены для хранения данных каждого документа.

- Реализация функции-члены для чтения и изменения данных документа. Наиболее важным пользователями эти функции-члены являются представления документа.

- Переопределить [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) функции-члена в классе документ для записи и чтения данных документа и с диска.

`CDocument` Поддержка отправки документа по почте, если имеется поддержка электронной почты (MAPI). См. в статьях [MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).

Дополнительные сведения о `CDocument`, см. в разделе [сериализации](../../mfc/serialization-in-mfc.md), [статьи по архитектуре документ/представление](../../mfc/document-view-architecture.md), и [создание документов и представлений](../../mfc/document-view-creation.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="addview"></a>  CDocument::AddView

Вызывайте эту функцию, чтобы присоединить представление документа.

```
void AddView(CView* pView);
```

### <a name="parameters"></a>Параметры

*pView*<br/>
Указывает добавляемый представления.

### <a name="remarks"></a>Примечания

Эта функция добавляет указанное представление в список представлений, связанных с документом; функция также задает указатель этого представления документа к этому документу. Платформа вызывает эту функцию, при присоединении объекта созданное новое представление в документ. Это происходит в ответ на команду новый файл, открыть файл или новое окно или при разбиении окна разделителя.

Вызывайте эту функцию только в том случае, если вы вручную создание и присоединение представления. Обычно позволит подключиться документов и представлений путем определения платформы [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объект для связывания класса документов, представления классов и класс окна фрейма.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

##  <a name="beginreadchunks"></a>  CDocument::BeginReadChunks

Инициализирует Фрагментирование чтения.

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>Примечания

##  <a name="cancloseframe"></a>  CDocument::CanCloseFrame

Вызывается средой перед закрытием окна фрейма, отображения документа.

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Параметры

*pFrame*<br/>
Указывает на фрейм окна представления, прикрепленного к документу.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если это безопасно закрыть окно фрейма; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию проверяет наличие других окон фрейма, отображения документа. Если окно заданного фрейма последний отображает документ, функция предлагает пользователю сохранить документ в том случае, если он был изменен. Переопределите эту функцию, если вы хотите выполнять специальную обработку при закрытии фрейма окна. Существует расширенная переопределяемый.

##  <a name="cdocument"></a>  CDocument::CDocument

Создает объект `CDocument`.

```
CDocument();
```

### <a name="remarks"></a>Примечания

Платформа обрабатывает создание документа для вас. Переопределить [OnNewDocument](#onnewdocument) функция-член для выполнения инициализации на основе каждого документа; это особенно важно в приложения с интерфейсом (SDI) одного документа.

##  <a name="clearchunklist"></a>  CDocument::ClearChunkList

Очищает список блоков.

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>Примечания

##  <a name="clearpathname"></a>  CDocument::ClearPathName

Очищает путь объекта документа.

```
virtual void ClearPathName();
```

### <a name="remarks"></a>Примечания

Очистка путь от `CDocument` объекта позволяет приложению запрашивать пользователя, когда документ сохраняется рядом. Это делает **Сохранить** команда ведут себя как **Сохранить как** команды.

##  <a name="deletecontents"></a>  CDocument::DeleteContents

Вызывается платформой для удаления данных документа без потерь `CDocument` сам объект.

```
virtual void DeleteContents();
```

### <a name="remarks"></a>Примечания

Он вызывается непосредственно перед началом документа будут уничтожены. Он также называется убедитесь, что документ пуст, прежде чем она будет использована повторно. Это особенно важно для приложения SDI, в котором используется только один документ; документ, повторно используется каждый раз, когда пользователь создает или открывает другой документ. Вызывайте эту функцию для реализации «Изменить очистить все», или же команду, которая удаляет все данные документа. Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию, чтобы удалить данные в документе.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

##  <a name="findchunk"></a>  CDocument::FindChunk

Ищет фрагмент данных с указанным идентификатором GUID.

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Параметры

*Идентификатор GUID*<br/>
Указывает GUID фрагмент для поиска.

*pid*<br/>
Указывает код продукта блока, для поиска.

### <a name="return-value"></a>Возвращаемое значение

Позиция в списке внутренних блоков при успешном выполнении. В противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

##  <a name="getadapter"></a>  CDocument::GetAdapter

Возвращает указатель на объект, реализующий интерфейс `IDocument` интерфейс.

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект, реализующий интерфейс `IDocument` интерфейс.

### <a name="remarks"></a>Примечания

##  <a name="getdoctemplate"></a>  CDocument::GetDocTemplate

Вызывайте эту функцию, чтобы получить указатель на шаблон документа для этого типа документа.

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на шаблон документа для данного типа документа или значение NULL, если документ не находится под управлением шаблон документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

##  <a name="getfile"></a>  CDocument::GetFile

Вызов этой функции-члена для получения указателя на `CFile` объекта.

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
Строка, — это путь к требуемому файлу. Путь может быть относительным или абсолютным.

*pError*<br/>
Указатель на объект исключения файлов, указывающее состояние завершения операции.

*nOpenFlags*<br/>
Совместное использование и режимом доступа. Указывает действие, выполняемое при открытии файла. Можно комбинировать параметры, перечисленные в конструкторе CFile [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) с помощью побитовой операции или (&#124;) оператор. Разрешение на доступ один параметр одну общую папку требуются и; `modeCreate` и `modeNoInherit` режимы являются необязательными.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CFile` .

##  <a name="getfirstviewposition"></a>  CDocument::GetFirstViewPosition

Вызывайте эту функцию для получения позиции первое представление в списке представлений, связанных с документом.

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, который может использоваться для итерации с помощью [GetNextView](#getnextview) функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getnextview"></a>  CDocument::GetNextView

Эта функция используется для перебора всех представлений документа.

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылку на значение ПОЗИЦИИ, возвращенный предыдущим вызовом `GetNextView` или [GetFirstViewPosition](#getfirstviewposition) функций-членов. Это значение не должно быть значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Указатель на представление, идентифицируемый *rPosition*.

### <a name="remarks"></a>Примечания

Функция возвращает представление, идентифицируемый *rPosition* и затем задает *rPosition* значению ПОЗИЦИИ следующее представление в списке. Если полученный это представление является последним в списке, затем *rPosition* имеет значение NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getpathname"></a>  CDocument::GetPathName

Вызывайте эту функцию, чтобы получить полный путь к файлу документа на диске.

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный путь документа. Эта строка является пустым, если документ не был сохранен, или не имеет связанный с ним файл на диске.

##  <a name="getthumbnail"></a>  CDocument::GetThumbnail

Создает растровое изображение, чтобы использоваться поставщика уменьшенных изображений, чтобы отобразить эскиз.

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>Параметры

*cx*<br/>
Указывает ширину и высоту растрового изображения.

*phbmp*<br/>
Содержит дескриптор к растровому изображению, когда функция возвращает успешно.

*pdwAlpha*<br/>
Содержит значение типа DWORD, указав значение альфа-канала, когда функция возвращает успешно.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если для эскиза растрового изображения был создан успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="gettitle"></a>  CDocument::GetTitle

Вызывайте эту функцию, чтобы получить название документа, который обычно является производным от имени файла документа.

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название документа.

##  <a name="initializesearchcontent"></a>  CDocument::InitializeSearchContent

Вызывается для инициализации для обработчика поиска поиск по содержимому.

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>Примечания

Переопределите этот метод в производном классе для инициализации поиск по содержимому. Содержимое должно быть строкой с частями, разделенные «;». Например «точек; прямоугольником. элемент OLE».

##  <a name="ismodified"></a>  CDocument::IsModified

Вызывайте эту функцию, чтобы определить, является ли документ был изменен с момента последнего сохранения.

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ был изменен с момента последнего сохранения; в противном случае 0.

##  <a name="issearchandorganizehandler"></a>  CDocument::IsSearchAndOrganizeHandler

Сообщает ли этот экземпляр `CDocument` был создан для поиска и организовать обработчика.

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если экземпляр `CDocument` был создан для поиска и организовать обработчика.

### <a name="remarks"></a>Примечания

В настоящее время эта функция возвращает значение TRUE только для обработчиков просмотра широкие возможности, реализованные в готовую сервер обработки. На уровне приложения, чтобы эта функция возвращает значение TRUE, можно задать соответствующие флаги (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode).

##  <a name="loaddocumentfromstream"></a>  CDocument::LoadDocumentFromStream

Вызывается, чтобы загрузить данные документа из потока.

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
Указатель на поток. Этот поток, предоставляемую оболочки.

*dwGrfMode*<br/>
Режим доступа к потоку.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция загрузки выполняется успешно, в противном случае — значение HRESULT с кодом ошибки.

### <a name="remarks"></a>Примечания

Можно переопределить этот метод в производном классе, чтобы настроить способ загрузки данных из потока.

##  <a name="m_bgetthumbnailmode"></a>  CDocument::m_bGetThumbnailMode

Указывает, что `CDocument` объект был создан при dllhost для эскизов. Должен быть установлен в `CView::OnDraw`.

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>Примечания

`TRUE` Указывает, что документ был создан с dllhost для эскизов.

##  <a name="m_bpreviewhandlermode"></a>  CDocument::m_bPreviewHandlerMode

Указывает, что `CDocument` объект был создан при prevhost для расширенного просмотра. Должен быть установлен в `CView::OnDraw`.

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>Примечания

Значение TRUE указывает, что документ был создан с prevhost для расширенного просмотра.

##  <a name="m_bsearchmode"></a>  CDocument::m_bSearchMode

Указывает, что `CDocument` индексатором или другим приложением поиска создан объект.

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>Примечания

`TRUE` Указывает, что был создан документ, индексатором или другим приложением поиска.

##  <a name="m_clrrichpreviewbackcolor"></a>  CDocument::m_clrRichPreviewBackColor

Задает цвет фона окна предварительного просмотра широкие возможности. Этот цвет задан узлом.

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>Примечания

##  <a name="m_clrrichpreviewtextcolor"></a>  CDocument::m_clrRichPreviewTextColor

Задает цвет переднего плана, окна предварительного просмотра широкие возможности. Этот цвет задан узлом.

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>Примечания

##  <a name="m_lfrichpreviewfont"></a>  CDocument::m_lfRichPreviewFont

Задает шрифт текста для окна предварительного просмотра широкие возможности. Эти сведения шрифта задается узлом.

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>Примечания

##  <a name="onbeforerichpreviewfontchanged"></a>  CDocument::OnBeforeRichPreviewFontChanged

Вызывается перед изменением шрифта расширенного просмотра.

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>Примечания

##  <a name="onchangedviewlist"></a>  CDocument::OnChangedViewList

Вызвано структурой после представления добавлении или удалении из документа.

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция проверяет ли последнее представление удаляется и, если это так, удаляет его. Переопределите эту функцию, если вы хотите выполнять специальную обработку, когда платформа добавляет или удаляет представление. Например документ оставаться открытым, даже в том случае, если нет представлений, подключенные к ней следует переопределите эту функцию.

##  <a name="onclosedocument"></a>  CDocument::OnCloseDocument

Вызывается платформой при закрытии документа, обычно в рамках команда закрытия файла.

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции уничтожает все кадры, используется для просмотра документа, закрывает представление, очищает содержимое документа, а затем вызывает [DeleteContents](#deletecontents) функция-член для удаления документа данные.

Переопределите эту функцию, если вы хотите выполнить специальные операции очистки обработки, когда платформа закрывает документ. Например если документ представляет запись в базу данных, может потребоваться переопределить эту функцию, чтобы закрыть базу данных. Версия этой функции базового класса следует вызывать из переопределение.

##  <a name="oncreatepreviewframe"></a>  CDocument::OnCreatePreviewFrame

Вызвано структурой при необходимости создать кадр предварительной версии для расширенного просмотра.

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если кадр будет создан успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

##  <a name="ondocumentevent"></a>  CDocument::OnDocumentEvent

Вызвано структурой в ответ на событие документа.

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>Параметры

*deEvent*<br/>
[in] Тип перечислимых данных, который описывает тип события.

### <a name="remarks"></a>Примечания

События документа может повлиять на несколько классов. Этот метод отвечает за обработку события документа, которые влияют на классы, отличные от [класс CDocument](../../mfc/reference/cdocument-class.md). В настоящее время является единственным классом, должны реагировать на события документа [класс CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md). `CDocument` Класс имеет другие переопределяемые методы, отвечающий за обработку эффект на `CDocument`.

В следующей таблице перечислены возможные значения для *deEvent* и события, которые они соответствуют.

|Значение|Соответствующее событие|
|-----------|-------------------------|
|`onAfterNewDocument`|Новый документ был создан.|
|`onAfterOpenDocument`|Новый документ был открыт.|
|`onAfterSaveDocument`|Документ был сохранен.|
|`onAfterCloseDocument`|Документ был закрыт.|

##  <a name="ondrawthumbnail"></a>  CDocument::OnDrawThumbnail

Переопределите этот метод в производном классе для рисования эскиз.

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>Параметры

*dc*<br/>
Ссылка на контекст устройства.

*lprcBounds*<br/>
Указывает ограничивающий прямоугольник области, где должен быть нарисован эскиз.

### <a name="remarks"></a>Примечания

##  <a name="onfilesendmail"></a>  CDocument::OnFileSendMail

Отправляет сообщение через обслуживания резидентного почты (если таковые имеются) в документе как вложение.

```
void OnFileSendMail();
```

### <a name="remarks"></a>Примечания

`OnFileSendMail` вызовы [OnSaveDocument](#onsavedocument) для сериализации (без названия и измененных документов во временный файл, который затем отправляется по электронной почте Сохранить). Если документ не был изменен, временный файл не требуется. отправляется исходный. `OnFileSendMail` Загружает MAPI32. Библиотека DLL, если он еще не загружена.

Специальные реализации `OnFileSendMail` для [COleDocument](../../mfc/reference/coledocument-class.md) обрабатывает составные файлы правильно.

`CDocument` Поддержка отправки документа по почте, если имеется поддержка электронной почты (MAPI). См. в статьях [разделы MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).

##  <a name="onloaddocumentfromstream"></a>  CDocument::OnLoadDocumentFromStream

Вызывается платформой, когда это необходимо загрузить данные документа из потока.

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>Параметры

*pStream*<br/>
Указатель на поток входящих.

*grfMode*<br/>
Режим доступа к потоку.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если загрузка прошла успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

##  <a name="onnewdocument"></a>  CDocument::OnNewDocument

Вызывается платформой как часть команды создания файла.

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ был успешно инициализирован; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция вызывает [DeleteContents](#deletecontents) функцию-член для убедитесь, что документ пуст, а затем помечает как чистый новому документу. Переопределите эту функцию, чтобы инициализировать структуру данных для нового документа. Версия этой функции базового класса следует вызывать из переопределение.

Если пользователь выбирает команды создания файла в приложении SDI, инфраструктура использует эту функцию для повторной инициализации существующих документов, а не создавать новую. Если пользователь выбирает новый файл в приложении несколько интерфейса (MDI) документа, платформа создает новый документ, каждый раз и затем вызывает эту функцию для инициализации. В этой функции, а не в конструкторе для команды создания файла для эффективного приложения SDI необходимо разместить код инициализации.

Обратите внимание, что существуют ситуации, когда `OnNewDocument` вызывается дважды. Это происходит, когда документ внедряется в виде сервер документов ActiveX. Сначала вызывается функция `CreateInstance` метод (предоставляемые `COleObjectFactory`-производного класса) и еще раз с `InitNew` метод (предоставляемые `COleServerDoc`-производного класса).

### <a name="example"></a>Пример

В следующих примерах показаны альтернативные методы инициализации объект документа.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

##  <a name="onopendocument"></a>  CDocument::OnOpenDocument

Вызывается платформой как часть команды открытия файла.

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Указывает путь для открываемого документа.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ был успешно загружен; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция открывает указанный файл, вызовы [DeleteContents](#deletecontents) убедитесь, что документ пуст, функция-член вызывает [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для чтения файла содержимое, а затем помечает его как чистый. Переопределите эту функцию, если вы хотите использовать что-то отличное от механизма архив или файл механизм. Например можно написать приложение, где документы представляют записи в базу данных, а не отдельные файлы.

Если пользователь выбирает команду «Открыть файл» в приложении SDI, инфраструктура использует эту функцию для повторной инициализации существующих `CDocument` объекта, а не создавать новую. Если пользователь выберет открытие файла в приложении MDI, платформа создает новое `CDocument` объект каждый раз, а затем вызывает эту функцию для инициализации. В этой функции, а не в конструкторе для команды открытия файла для эффективного приложения SDI необходимо разместить код инициализации.

### <a name="example"></a>Пример

В следующих примерах показаны альтернативные методы инициализации объект документа.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

##  <a name="onpreviewhandlerqueryfocus"></a>  CDocument::OnPreviewHandlerQueryFocus

Направляет обработчик просмотра для возврата HWND полученные из вызова метода `GetFocus` функции.

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>Параметры

*phwnd*<br/>
[out] При возвращении данного метода содержит указатель на HWND, возвращенные из вызова `GetFocus` функцию из основного потока обработчика просмотра.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK, если выполнение прошло успешно; или, в противном случае значение ошибки.

### <a name="remarks"></a>Примечания

##  <a name="onpreviewhandlertranslateaccelerator"></a>  CDocument::OnPreviewHandlerTranslateAccelerator

Направляет обработчик просмотра для обработки нажатия клавиш, передаются из средства переноса сообщений процесс, в которой выполняется обработчик просмотра.

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>Параметры

*pmsg*<br/>
[in] Указатель на окно сообщения.

### <a name="return-value"></a>Возвращаемое значение

Если сообщение регистрации нажатия клавиш могут обрабатываться обработчика просмотра, обработчик обрабатывает его и возвращает значение S_OK. Если обработчик просмотра не может обработать сообщение регистрации нажатия клавиш, он предлагает его к узлу через `IPreviewHandlerFrame::TranslateAccelerator`. Если узел обрабатывает сообщение, этот метод возвращает значение S_OK. Если узел не обрабатывает сообщение, этот метод возвращает значение S_FALSE.

### <a name="remarks"></a>Примечания

##  <a name="onrichpreviewbackcolorchanged"></a>  CDocument::OnRichPreviewBackColorChanged

Вызывается, когда изменился цвет фона расширенного просмотра.

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>Примечания

##  <a name="onrichpreviewfontchanged"></a>  CDocument::OnRichPreviewFontChanged

Вызывается при изменении шрифта расширенного просмотра.

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>Примечания

##  <a name="onrichpreviewsitechanged"></a>  CDocument::OnRichPreviewSiteChanged

Вызывается при изменении расширенного просмотра сайта.

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>Примечания

##  <a name="onrichpreviewtextcolorchanged"></a>  CDocument::OnRichPreviewTextColorChanged

Вызывается при изменении цвета текста расширенного просмотра.

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>Примечания

##  <a name="onsavedocument"></a>  CDocument::OnSaveDocument

Вызывается платформой как часть команды "Сохранить файл" или "Сохранить как файл.

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Указывает полный путь, к которому следует сохранить файл.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ был успешно сохранен; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция открывает указанный файл, вызовы [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для записи данных документа в файл, а затем метки документ как очистить. Переопределите эту функцию, если вы хотите выполнять специальную обработку, когда платформа сохраняет документ. Например можно написать приложение, где документы представляют записи в базу данных, а не отдельные файлы.

##  <a name="onunloadhandler"></a>  CDocument::OnUnloadHandler

Вызывается платформой при выгрузке обработчика просмотра.

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>Примечания

##  <a name="onupdatefilesendmail"></a>  CDocument::OnUpdateFileSendMail

Становится доступной команда ID_FILE_SEND_MAIL, если имеется поддержка электронной почты (MAPI).

```
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*pCmdUI*<br/>
Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объект, связанный с командой ID_FILE_SEND_MAIL.

### <a name="remarks"></a>Примечания

В противном случае функция удаляет ID_FILE_SEND_MAIL команду меню, включая разделители выше или ниже пункта меню, соответствующим образом. MAPI доступен в том случае, если MAPI32. DLL присутствует по пути и в разделе [Mail] WIN. INI-файл, MAPI = 1. Большинство приложений поместить эту команду в меню "файл".

`CDocument` Поддержка отправки документа по почте, если имеется поддержка электронной почты (MAPI). См. в статьях [разделы MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).

##  <a name="precloseframe"></a>  CDocument::PreCloseFrame

Эта функция-член вызывается платформой перед уничтожением фрейма окна.

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Параметры

*pFrame*<br/>
Указатель на [CFrameWnd](../../mfc/reference/cframewnd-class.md) , содержащий связанный `CDocument` объекта.

### <a name="remarks"></a>Примечания

Его можно переопределить, чтобы предоставить пользовательскую очистку, но не забудьте вызвать базовый класс также.

Значение по умолчанию `PreCloseFrame` не выполняет никаких действий `CDocument`. `CDocument`-Производные классы [COleDocument](../../mfc/reference/coledocument-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) использовать эту функцию-член.

##  <a name="readnextchunkvalue"></a>  CDocument::ReadNextChunkValue

Считывает следующее значение фрагмента данных.

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>Параметры

*ppValue*<br/>
[out] При возврате функции, *ppValue* содержит значение, которое было считано.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

##  <a name="releasefile"></a>  CDocument::ReleaseFile

Эта функция-член вызывается платформой для освобождения файла, делая его доступным для использования другими приложениями.

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>Параметры

*pFile*<br/>
Указатель на объект CFile, освобождается.

*bAbort*<br/>
Указывает, является ли файл быть освобожден с помощью `CFile::Close` или `CFile::Abort`. Значение FALSE, если файл должен освобождаться с помощью [CFile::Close](../../mfc/reference/cfile-class.md#close); Значение TRUE, если файл должен освобождаться с помощью [CFile::Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="remarks"></a>Примечания

Если *bAbort* имеет значение TRUE, `ReleaseFile` вызовы `CFile::Abort`, и файл освобождается. `CFile::Abort` не вызовет исключение.

Если *bAbort* имеет значение FALSE, `ReleaseFile` вызовы `CFile::Close` и файл освобождается.

Переопределите эту функцию-член требуется действие пользователя перед выпуском файл.

##  <a name="removechunk"></a>  CDocument::RemoveChunk

Удаляет фрагмент данных с указанным идентификатором GUID.

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Параметры

*Guid*<br/>
Указывает идентификатор GUID удаляемого блока.

*Идентификатор процесса*<br/>
Указывает идентификатор Процесса удаляемого блока.

### <a name="remarks"></a>Примечания

##  <a name="removeview"></a>  CDocument::RemoveView

Вызывайте эту функцию, чтобы отключить представление из документа.

```
void RemoveView(CView* pView);
```

### <a name="parameters"></a>Параметры

*pView*<br/>
Указывает представление удаления.

### <a name="remarks"></a>Примечания

Эта функция удаляет указанное представление из списка представлений, связанных с документом; Он также задает представление документа указатель NULL. Эта функция вызывается платформой при закрытии фрейма окна или при закрытии панели окна-разделителя.

Вызывайте эту функцию только в том случае, если вы вручную отсоединение представления. Обычно позволит платформа отсоединение документов и представлений, определив [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объект для связывания класса документов, представления классов и класс окна фрейма.

См. пример в [добавить представление](#addview) образец реализации.

##  <a name="reportsaveloadexception"></a>  CDocument::ReportSaveLoadException

Вызывается, если создается исключение (обычно [CFileException](../../mfc/reference/cfileexception-class.md) или [CArchiveException](../../mfc/reference/carchiveexception-class.md)) во время сохранения или загрузки документа.

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Указывает имя документа, которая находится в процессе сохранения или загрузки.

*e*<br/>
Указывает исключение, вызванное исключение. Может иметь значение NULL.

*bSaving*<br/>
Флаг, указывающий, какая операция выполнялась; ненулевое значение, если его сохранении, 0, если при загрузке документа.

*nIDPDefault*<br/>
Идентификатор сообщения об ошибке, отображаемое, если функция не содержит более конкретным предложениям.

### <a name="remarks"></a>Примечания

Реализация по умолчанию проверяет объект исключения и ищет сообщение об ошибке, в частности, описывающее причину. Если сообщение не найден или *e* имеет значение NULL, общие сообщению, заданному параметром *nIDPDefault* используется параметр. Функции выводится окно сообщения, содержащее сообщение об ошибке. Переопределите эту функцию, если вы хотите предоставить дополнительные, настраиваемых сообщений. Существует расширенная переопределяемый.

##  <a name="savemodified"></a>  CDocument::SaveModified

Вызвано структурой перед измененный документ будет закрыт.

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если это безопасно продолжить и закрыть документ; 0, если документ не должен быть закрыт.

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция отображает окно сообщения с запросом пользователя, следует ли сохранить изменения в документе, если они были внесены. Переопределите эту функцию, если программе требуется другой процедуры запроса. Существует расширенная переопределяемый.

##  <a name="setchunkvalue"></a>  CDocument::SetChunkValue

Задает значение фрагмента данных.

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Указывает значение фрагмента данных.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

##  <a name="setmodifiedflag"></a>  CDocument::SetModifiedFlag

Вызывайте эту функцию после внесения изменения в документе.

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Параметры

*bModified*<br/>
Флаг, указывающий, был ли документ изменен.

### <a name="remarks"></a>Примечания

Путем вызова этой функции постоянно, убедитесь, что платформа будет предложено сохранить изменения перед закрытием документа. Обычно следует использовать значение по умолчанию true для *bModified* параметра. Чтобы пометить документ как очистить (без изменений), эта функция вызывается со значением FALSE.

##  <a name="setpathname"></a>  CDocument::SetPathName

Вызывайте эту функцию, чтобы указать полный путь к файлу документа на диске.

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Указывает на строку для использования в качестве пути для документа.

*bAddToMRU*<br/>
Определяет, является ли имя файла добавляется к наиболее часто используемое список файлов (MRU). Если значение равно TRUE, добавляется имя файла; Если значение равно FALSE, он не добавляется.

### <a name="remarks"></a>Примечания

В зависимости от значения *bAddToMRU* добавляется путь, или не добавлен в список последних выбиравшихся файлов, обслуживаются приложением. Обратите внимание на то, что некоторые документы не связаны с файлом на диске. Вызывайте эту функцию только в том случае, если вы переопределяете реализация по умолчанию для открытия и сохранения файлов, используемых платформой.

##  <a name="settitle"></a>  CDocument::SetTitle

Вызывайте эту функцию, чтобы указать название документа (строка, отображаемая в строке заголовка окна фрейма).

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Параметры

*lpszTitle*<br/>
Указывает на строку для использования в качестве название документа.

### <a name="remarks"></a>Примечания

Вызов этой функции обновляет названия всех окон фрейма, отобразить документ.

##  <a name="updateallviews"></a>  CDocument::UpdateAllViews

Эта функция вызывается после изменения документа.

```
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>Параметры

*pSender*<br/>
Указывает представление, измененный документ, или значение NULL, если все представления должны быть обновлены.

*lHint*<br/>
Содержит сведения об изменении.

*pHint*<br/>
Указывает на объект хранения сведения об изменении.

### <a name="remarks"></a>Примечания

Эту функцию следует вызывать после вызова метода [SetModifiedFlag](#setmodifiedflag) функция-член. Эта функция сообщает каждого представления, прикрепленного к документу, за исключением представление, задаваемое *pSender*, что документ был изменен. Обычно эта функция вызывается из класса представления после документа через представление было изменено пользователем.

Эта функция вызывает [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) просмотреть функция-член для каждого из представления документа, за исключением отправку, передав *pHint* и *lHint*. Эти параметры можно используйте для передачи информации представления об изменениях, внесенных в документ. Можно закодировать с помощью *lHint* и/или можно определить [CObject](../../mfc/reference/cobject-class.md)-производный класс для хранения информации об изменениях и передайте объект этого класса, используя *pHint*. Переопределить `CView::OnUpdate` функции-члена в вашей [CView](../../mfc/reference/cview-class.md)-производный класс для оптимизации обновления на информацию, передаваемую в основе отображения представления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC MDIDOCVW](../../visual-cpp-samples.md)<br/>
[Пример MFC: SNAPVW](../../visual-cpp-samples.md)<br/>
[Пример MFC NPP](../../visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)
