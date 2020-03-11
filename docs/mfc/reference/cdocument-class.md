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
ms.openlocfilehash: 2d87ff67000fb5b70c0a5c965638875e6f50b22c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856765"
---
# <a name="cdocument-class"></a>Класс CDocument

Предоставляет базовую функциональность для определяемых пользователем классов документа.

## <a name="syntax"></a>Синтаксис

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CDocument:: CDocument](#cdocument)|Формирует объект `CDocument`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[CDocument:: Аддвиев](#addview)|Присоединяет представление к документу.|
|[CDocument:: Бегинреадчункс](#beginreadchunks)|Инициализирует Считывание фрагментов.|
|[CDocument:: Канклосефраме](#cancloseframe)|Расширенная переопределяемая; вызывается перед закрытием окна фрейма, просматривающего этот документ.|
|[CDocument:: Клеарчунклист](#clearchunklist)|Очищает список фрагментов.|
|[CDocument:: Клеарпаснаме](#clearpathname)|Очищает путь к объекту документа.|
|[CDocument::D Елетеконтентс](#deletecontents)|Вызывается для выполнения очистки документа.|
|[CDocument:: Финдчунк](#findchunk)|Ищет фрагмент с указанным GUID.|
|[CDocument:: адаптер](#getadapter)|Возвращает указатель на объект, реализующий интерфейс `IDocument`.|
|[CDocument:: Жетдоктемплате](#getdoctemplate)|Возвращает указатель на шаблон документа, описывающий тип документа.|
|[CDocument:: файл](#getfile)|Возвращает указатель на нужный объект `CFile`.|
|[CDocument:: Жетфирствиевпоситион](#getfirstviewposition)|Возвращает расположение первого объекта в списке представлений; используется для начала итерации.|
|[CDocument:: Жетнекствиев](#getnextview)|Выполняет итерацию по списку представлений, связанных с документом.|
|[CDocument:: путь](#getpathname)|Возвращает путь к файлу данных документа.|
|[CDocument:: thumbnail](#getthumbnail)|Вызывается для создания точечного рисунка, используемого поставщиком эскизов для показа эскиза.|
|[CDocument::/Title](#gettitle)|Возвращает заголовок документа.|
|[CDocument:: Инитиализесеарчконтент](#initializesearchcontent)|Вызывается для инициализации содержимого поиска для обработчика поиска.|
|[CDocument:: Modified](#ismodified)|Указывает, был ли документ изменен с момента последнего сохранения.|
|[CDocument:: Иссеарчандорганизехандлер](#issearchandorganizehandler)|Сообщает, был ли создан экземпляр `CDocument`ного объекта для поиска & Организации обработчика.|
|[CDocument:: Лоаддокументфромстреам](#loaddocumentfromstream)|Вызывается для загрузки данных документа из потока.|
|[CDocument:: Онбефореричпревиевфонтчанжед](#onbeforerichpreviewfontchanged)|Вызывается до изменения расширенного шрифта предварительной версии.|
|[CDocument:: Ончанжедвиевлист](#onchangedviewlist)|Вызывается после добавления представления в документ или удаления из него.|
|[CDocument:: Онклоседокумент](#onclosedocument)|Вызывается для закрытия документа.|
|[CDocument:: Онкреатепревиевфраме](#oncreatepreviewframe)|Вызывается платформой при необходимости создать предварительный просмотр кадра для расширенного просмотра.|
|[CDocument:: Ондокументевент](#ondocumentevent)|Вызывается платформой в ответ на событие документа.|
|[CDocument:: OnDrawThumbnail](#ondrawthumbnail)|Переопределите этот метод в производном классе, чтобы нарисовать содержимое эскиза.|
|[CDocument:: Онлоаддокументфромстреам](#onloaddocumentfromstream)|Вызывается структурой при необходимости загрузки данных документа из потока.|
|[CDocument:: Онневдокумент](#onnewdocument)|Вызывается для создания нового документа.|
|[CDocument:: OnOpenDocument](#onopendocument)|Вызывается для открытия существующего документа.|
|[CDocument:: Онпревиевхандлеркуерифокус](#onpreviewhandlerqueryfocus)|Направляет обработчик просмотра для возврата HWND из вызова функции Focus.|
|[CDocument:: Онпревиевхандлертранслатеакцелератор](#onpreviewhandlertranslateaccelerator)|Направляет обработчик просмотра для обработки нажатия клавиши, передаваемой из конвейера сообщений процесса, в котором выполняется обработчик просмотра.|
|[CDocument:: Онричпревиевбаккколорчанжед](#onrichpreviewbackcolorchanged)|Вызывается, когда изменился цвет фона для расширенного просмотра.|
|[CDocument:: Онричпревиевфонтчанжед](#onrichpreviewfontchanged)|Вызывается, когда изменен насыщенный цвет для просмотра.|
|[CDocument:: Онричпревиевситечанжед](#onrichpreviewsitechanged)|Вызывается, когда изменился сайт расширенного просмотра.|
|[CDocument:: Онричпревиевтекстколорчанжед](#onrichpreviewtextcolorchanged)|Вызывается, когда изменился цвет текста для расширенного просмотра.|
|[CDocument:: Онсаведокумент](#onsavedocument)|Вызывается для сохранения документа на диск.|
|[CDocument:: Онунлоадхандлер](#onunloadhandler)|Вызывается структурой при выгрузке обработчика просмотра.|
|[CDocument::P Реклосефраме](#precloseframe)|Вызывается перед закрытием окна фрейма.|
|[CDocument:: Реаднекстчунквалуе](#readnextchunkvalue)|Считывает следующее значение блока.|
|[CDocument:: Релеасефиле](#releasefile)|Освобождает файл, чтобы сделать его доступным для использования другими приложениями.|
|[CDocument:: Ремовечунк](#removechunk)|Удаляет блок с указанным GUID.|
|[CDocument:: Ремовевиев](#removeview)|Отсоединяет представление от документа.|
|[CDocument:: Репортсавелоадексцептион](#reportsaveloadexception)|Расширенная переопределяемая; вызывается, когда операция открытия или сохранения не может быть завершена из-за исключения.|
|[CDocument:: Савемодифиед](#savemodified)|Расширенная переопределяемая; вызывается для запроса пользователя, следует ли сохранить документ.|
|[CDocument:: Сетчунквалуе](#setchunkvalue)|Задает значение фрагмента.|
|[CDocument:: SetModifiedFlag](#setmodifiedflag)|Задает флаг, указывающий, что документ был изменен с момента последнего сохранения.|
|[CDocument:: Сетпаснаме](#setpathname)|Задает путь к файлу данных, используемому документом.|
|[CDocument:: Сеттитле](#settitle)|Задает заголовок документа.|
|[CDocument:: UpdateAllViews](#updateallviews)|Уведомляет все представления, которые были изменены в документе.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[CDocument:: Онфилесендмаил](#onfilesendmail)|Отправляет почтовое сообщение с прикрепленным документом.|
|[CDocument:: Онупдатефилесендмаил](#onupdatefilesendmail)|Включает команду Отправить почту, если имеется поддержка по почте.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Description|
|----------|-----------------|
|[CDocument:: m_bGetThumbnailMode](#m_bgetthumbnailmode)|Указывает, что в dllhost для эскизов был создан объект `CDocument`. Должен быть возвращен в `CView::OnDraw`.|
|[CDocument:: m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Указывает, что `CDocument` объект был создан с помощью prevhost для `Rich Preview`. Должен быть возвращен в `CView::OnDraw`.|
|[CDocument:: m_bSearchMode](#m_bsearchmode)|Указывает, что `CDocument` объект был создан индексатором или другим приложением поиска.|
|[CDocument:: m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Задает цвет фона окна расширенного просмотра. Этот цвет задается узлом.|
|[CDocument:: m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Задает цвет переднего плана для окна расширенного просмотра. Этот цвет задается узлом.|
|[CDocument:: m_lfRichPreviewFont](#m_lfrichpreviewfont)|Задает шрифт текста для расширенного окна предварительного просмотра. Эти сведения о шрифтах задаются узлом.|

## <a name="remarks"></a>Remarks

Документ представляет единицу данных, которую обычно открывает пользователь с помощью команды File Open, и сохраняет ее с помощью команды File Save.

`CDocument` поддерживает стандартные операции, такие как создание документа, его загрузка и сохранение. Платформа управляет документами с помощью интерфейса, определенного `CDocument`.

Приложение может поддерживать несколько типов документов. Например, приложение может поддерживать как электронные таблицы, так и текстовые документы. С каждым типом документа связан шаблон документа; шаблон документа указывает, какие ресурсы (например, меню, значок или таблица сочетаний клавиш) используются для этого типа документа. Каждый документ содержит указатель на связанный с ним объект `CDocTemplate`.

Пользователи взаимодействуют с документом через связанные с ним объекты [CView](../../mfc/reference/cview-class.md) . Представление отображает изображение документа в окне фрейма и интерпретирует ввод пользователя как операции над документом. С документом может быть связано несколько представлений. Когда пользователь открывает окно в документе, платформа создает представление и прикрепляет его к документу. Шаблон документа определяет, какой тип представления и окна фрейма используются для отображения каждого типа документа.

Документы являются частью стандартной маршрутизации команд в инфраструктуре и поэтому получают команды из стандартных компонентов пользовательского интерфейса (например, пункта меню "сохранить файл"). Документ получает команды, перенаправляемые активным представлением. Если документ не обрабатывает указанную команду, он пересылает команду в шаблон документа, который управляет им.

При изменении данных документа каждое из его представлений должно отражать эти изменения. `CDocument` предоставляет функцию члена [UpdateAllViews](#updateallviews) для уведомления о представлениях таких изменений, поэтому при необходимости представления могут перерисовываться. Платформа также предлагает пользователю сохранить измененный файл перед закрытием.

Для реализации документов в типичном приложении необходимо выполнить следующие действия.

- Создайте класс, производный от `CDocument` для каждого типа документа.

- Добавьте переменные члена для хранения данных каждого документа.

- Реализуйте функции элементов для чтения и изменения данных документа. Представления документа являются наиболее важными пользователями этих функций элементов.

- Переопределите функцию члена [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) в классе документа для записи и чтения данных документа на диск и с диска.

`CDocument` поддерживает отправку документа по электронной почте, если имеется поддержка почты (MAPI). См. статьи поддержка [MAPI](../../mfc/mapi.md) и [MAPI в MFC](../../mfc/mapi-support-in-mfc.md).

Дополнительные сведения о `CDocument`см. в разделах [сериализация](../../mfc/serialization-in-mfc.md), [документирование и просмотр архитектуры](../../mfc/document-view-architecture.md), а также [Создание документов и представлений](../../mfc/document-view-creation.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="addview"></a>CDocument:: Аддвиев

Вызовите эту функцию, чтобы присоединить представление к документу.

```
void AddView(CView* pView);
```

### <a name="parameters"></a>Параметры

*pView*<br/>
Указывает на добавляемое представление.

### <a name="remarks"></a>Remarks

Эта функция добавляет указанное представление в список представлений, связанных с документом. функция также задает указатель документа представления в этом документе. Платформа вызывает эту функцию при присоединении вновь созданного объекта представления к документу. Это происходит в ответ на команду Создать файл, открыть файл или создать окно или при разбиении окна разделителя.

Вызывайте эту функцию только в том случае, если вы вручную создаете и присоединяете представление. Как правило, платформа позволяет подключать документы и представления, определяя объект [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) для связывания класса документа, класса представления и класс окна фрейма.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

##  <a name="beginreadchunks"></a>CDocument:: Бегинреадчункс

Инициализирует Считывание фрагментов.

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>Remarks

##  <a name="cancloseframe"></a>CDocument:: Канклосефраме

Вызывается структурой перед закрытием окна фрейма, отображающего документ.

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Параметры

*пфраме*<br/>
Указывает на окно фрейма представления, присоединенного к документу.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если окно фрейма можно закрыть; в противном случае — 0.

### <a name="remarks"></a>Remarks

Реализация по умолчанию проверяет наличие других окон фрейма, отображающих документ. Если указанное окно фрейма является последним, отображающим документ, функция предложит пользователю сохранить документ, если он был изменен. Переопределите эту функцию, если требуется выполнить специальную обработку при закрытии окна фрейма. Это расширенный переопределяемый объект.

##  <a name="cdocument"></a>CDocument:: CDocument

Формирует объект `CDocument`.

```
CDocument();
```

### <a name="remarks"></a>Remarks

Платформа обрабатывает создание документов. Переопределите функцию-член [онневдокумент](#onnewdocument) для выполнения инициализации для каждого документа; Это особенно важно в приложениях с одним документом (SDI).

##  <a name="clearchunklist"></a>CDocument:: Клеарчунклист

Очищает список фрагментов.

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>Remarks

##  <a name="clearpathname"></a>CDocument:: Клеарпаснаме

Очищает путь к объекту документа.

```
virtual void ClearPathName();
```

### <a name="remarks"></a>Remarks

Очистка пути от объекта `CDocument` заставляет приложение запрашивать пользователя при следующем сохранении документа. При этом команда **сохранения** работает так же, как команда **Сохранить как** .

##  <a name="deletecontents"></a>CDocument::D Елетеконтентс

Вызвано платформой для удаления данных документа без удаления самого объекта `CDocument`.

```
virtual void DeleteContents();
```

### <a name="remarks"></a>Remarks

Он вызывается непосредственно перед уничтожением документа. Он также вызывается, чтобы убедиться, что документ пуст, прежде чем он будет использован повторно. Это особенно важно для приложения SDI, в котором используется только один документ. документ повторно используется каждый раз, когда пользователь создает или открывает другой документ. Эта функция вызывается для реализации команды "изменить очистить все" или аналогичной командой, которая удаляет все данные документа. Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию, чтобы удалить данные из документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

##  <a name="findchunk"></a>CDocument:: Финдчунк

Ищет фрагмент с указанным GUID.

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Параметры

*guid*<br/>
Указывает идентификатор GUID искомого фрагмента.

*pid*<br/>
Указывает идентификатор процесса искомого фрагмента.

### <a name="return-value"></a>Возвращаемое значение

При успешном размещении во внутреннем списке блоков. В противном случае — NULL.

### <a name="remarks"></a>Remarks

##  <a name="getadapter"></a>CDocument:: адаптер

Возвращает указатель на объект, реализующий интерфейс `IDocument`.

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект, реализующий интерфейс `IDocument`.

### <a name="remarks"></a>Remarks

##  <a name="getdoctemplate"></a>CDocument:: Жетдоктемплате

Вызовите эту функцию, чтобы получить указатель на шаблон документа для этого типа документа.

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на шаблон документа для этого типа документа или значение NULL, если документ не управляется шаблоном документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

##  <a name="getfile"></a>CDocument:: файл

Вызовите эту функцию-член для получения указателя на объект `CFile`.

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>Параметры

*лпсзфиленаме*<br/>
Строка, которая является путем к требуемому файлу. Путь может быть относительным или абсолютным.

*pError*<br/>
Указатель на существующий объект исключения файла, указывающий состояние завершения операции.

*нопенфлагс*<br/>
Общий доступ и режим доступа. Указывает действие, выполняемое при открытии файла. Параметры, перечисленные в конструкторе Кфиле [кфиле:: кфиле](../../mfc/reference/cfile-class.md#cfile) , можно объединять с помощью побитового оператора OR (&#124;). Требуется одно разрешение на доступ и один параметр общего ресурса; режимы `modeCreate` и `modeNoInherit` необязательны.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CFile`.

##  <a name="getfirstviewposition"></a>CDocument:: Жетфирствиевпоситион

Вызовите эту функцию, чтобы получить расположение первого представления в списке представлений, связанных с документом.

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение расположения, которое можно использовать для итерации с функцией-членом [жетнекствиев](#getnextview) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getnextview"></a>CDocument:: Жетнекствиев

Вызовите эту функцию, чтобы выполнить итерацию всех представлений документа.

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылка на значение координаты, возвращенное предыдущим вызовом функций-членов `GetNextView` или [жетфирствиевпоситион](#getfirstviewposition) . Это значение не должно быть равно NULL.

### <a name="return-value"></a>Возвращаемое значение

Указатель на представление, определяемое параметром *rPosition*.

### <a name="remarks"></a>Remarks

Функция возвращает представление, определяемое параметром *rPosition* , а затем устанавливает *rPosition* в значение value следующего представления в списке. Если полученное представление является последним в списке, *rPosition* имеет значение null.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

##  <a name="getpathname"></a>CDocument:: путь

Вызовите эту функцию, чтобы получить полный путь к файлу документа на диске.

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный путь к документу. Эта строка пуста, если документ не был сохранен или с ним не связан файл диска.

##  <a name="getthumbnail"></a>CDocument:: thumbnail

Создает точечный рисунок, используемый поставщиком эскиза для вывода эскиза.

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>Параметры

*cx*<br/>
Задает ширину и высоту точечного рисунка.

*фбмп*<br/>
Содержит маркер для точечного рисунка, когда функция возвращается успешно.

*пдвалфа*<br/>
Содержит параметр DWORD, указывающий значение альфа-канала при успешном возврате функции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если точечный рисунок для эскиза был успешно создан. в противном случае — FALSE.

### <a name="remarks"></a>Remarks

##  <a name="gettitle"></a>CDocument::/Title

Вызовите эту функцию, чтобы получить заголовок документа, который обычно является производным от имени файла документа.

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Заголовок документа.

##  <a name="initializesearchcontent"></a>CDocument:: Инитиализесеарчконтент

Вызывается для инициализации содержимого поиска для обработчика поиска.

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>Remarks

Переопределите этот метод в производном классе, чтобы инициализировать содержимое поиска. Содержимое должно быть строкой с частями, разделенными символом ";". Например, "точка; углами элемент OLE».

##  <a name="ismodified"></a>CDocument:: Modified

Вызовите эту функцию, чтобы определить, изменился ли документ с момента последнего сохранения.

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ был изменен с момента последнего сохранения; в противном случае — 0.

##  <a name="issearchandorganizehandler"></a>CDocument:: Иссеарчандорганизехандлер

Сообщает, был ли создан экземпляр `CDocument` для обработчика поиска & Организации.

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если этот экземпляр `CDocument` был создан для обработчика поиска & Организации.

### <a name="remarks"></a>Remarks

В настоящее время эта функция возвращает значение TRUE только для расширенных обработчиков просмотра, реализованных на сервере вне обработки. Можно задать соответствующие флаги (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) на уровне приложения, чтобы эта функция возвращала значение TRUE.

##  <a name="loaddocumentfromstream"></a>CDocument:: Лоаддокументфромстреам

Вызывается для загрузки данных документа из потока.

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
Указатель на поток. Этот поток предоставляется оболочкой.

*двгрфмоде*<br/>
Режим доступа к потоку.

### <a name="return-value"></a>Возвращаемое значение

S_OK, если операция загрузки завершилась с ошибкой, в противном случае — HRESULT с кодом ошибки.

### <a name="remarks"></a>Remarks

Этот метод можно переопределить в производном классе, чтобы настроить способ загрузки данных из потока.

##  <a name="m_bgetthumbnailmode"></a>CDocument:: m_bGetThumbnailMode

Указывает, что объект `CDocument` был создан dllhost для эскизов. Должен быть возвращен в `CView::OnDraw`.

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>Remarks

`TRUE` указывает, что документ был создан dllhost для эскизов.

##  <a name="m_bpreviewhandlermode"></a>CDocument:: m_bPreviewHandlerMode

Указывает, что объект `CDocument` был создан с помощью prevhost для расширенной предварительной версии. Должен быть возвращен в `CView::OnDraw`.

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>Remarks

Значение TRUE указывает, что документ был создан с помощью prevhost для расширенной предварительной версии.

##  <a name="m_bsearchmode"></a>CDocument:: m_bSearchMode

Указывает, что объект `CDocument` был создан индексатором или другим приложением поиска.

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>Remarks

`TRUE` указывает, что документ был создан индексатором или другим приложением поиска.

##  <a name="m_clrrichpreviewbackcolor"></a>CDocument:: m_clrRichPreviewBackColor

Задает цвет фона для расширенного окна предварительного просмотра. Этот цвет задается узлом.

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>Remarks

##  <a name="m_clrrichpreviewtextcolor"></a>CDocument:: m_clrRichPreviewTextColor

Задает цвет переднего плана для расширенного окна предварительного просмотра. Этот цвет задается узлом.

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>Remarks

##  <a name="m_lfrichpreviewfont"></a>CDocument:: m_lfRichPreviewFont

Задает шрифт текста для расширенного окна предварительного просмотра. Эти сведения о шрифтах задаются узлом.

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>Remarks

##  <a name="onbeforerichpreviewfontchanged"></a>CDocument:: Онбефореричпревиевфонтчанжед

Вызывается до изменения шрифта с расширенным просмотром.

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="onchangedviewlist"></a>CDocument:: Ончанжедвиевлист

Вызывается структурой после добавления представления в документ или удаления из него.

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>Remarks

Реализация по умолчанию этой функции проверяет, удаляется ли последнее представление, и, если да, удаляет документ. Переопределите эту функцию, если требуется выполнить специальную обработку, когда платформа добавляет или удаляет представление. Например, если необходимо, чтобы документ оставался открытым даже при отсутствии вложенных представлений, переопределите эту функцию.

##  <a name="onclosedocument"></a>CDocument:: Онклоседокумент

Вызывается платформой при закрытии документа, обычно как часть команды Close файла.

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>Remarks

Реализация по умолчанию этой функции уничтожает все кадры, используемые для просмотра документа, закрывает представление, очищает содержимое документа, а затем вызывает функцию члена [делетеконтентс](#deletecontents) для удаления данных документа.

Переопределите эту функцию, если требуется выполнить специальную обработку очистки, когда платформа закрывает документ. Например, если документ представляет запись в базе данных, может потребоваться переопределить эту функцию, чтобы закрыть базу данных. Следует вызывать версию базового класса этой функции из переопределения.

##  <a name="oncreatepreviewframe"></a>CDocument:: Онкреатепревиевфраме

Вызывается платформой при необходимости создать предварительный просмотр кадра для расширенного просмотра.

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если кадр создан успешно. в противном случае — FALSE.

### <a name="remarks"></a>Remarks

##  <a name="ondocumentevent"></a>CDocument:: Ондокументевент

Вызывается платформой в ответ на событие документа.

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>Параметры

*с четностью*<br/>
окне Перечислимый тип данных, описывающий тип события.

### <a name="remarks"></a>Remarks

События документа могут повлиять на несколько классов. Этот метод отвечает за обработку событий документа, которые влияют на классы, отличные от [класса CDocument](../../mfc/reference/cdocument-class.md). В настоящее время единственным классом, который должен отвечать на события документа, является [класс кдатарековерихандлер](../../mfc/reference/cdatarecoveryhandler-class.md). Класс `CDocument` имеет другие переопределяемые методы, отвечающие за обработку воздействия на `CDocument`.

В следующей таблице перечислены возможные значения для, *а также* связанные с ними события.

|Значение|Соответствующее событие|
|-----------|-------------------------|
|`onAfterNewDocument`|Создан новый документ.|
|`onAfterOpenDocument`|Был открыт новый документ.|
|`onAfterSaveDocument`|Документ был сохранен.|
|`onAfterCloseDocument`|Документ был закрыт.|

##  <a name="ondrawthumbnail"></a>CDocument:: OnDrawThumbnail

Переопределите этот метод в производном классе, чтобы нарисовать эскиз.

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>Параметры

*dc*<br/>
Ссылка на контекст устройства.

*лпркбаундс*<br/>
Задает ограничивающий прямоугольник области, в которой должен быть нарисован эскиз.

### <a name="remarks"></a>Remarks

##  <a name="onfilesendmail"></a>CDocument:: Онфилесендмаил

Отправляет сообщение через узел резидентной почты (если есть) с документом в качестве вложения.

```
void OnFileSendMail();
```

### <a name="remarks"></a>Remarks

`OnFileSendMail` вызывает [онсаведокумент](#onsavedocument) для сериализации (сохранения) безымянных и измененных документов во временный файл, который затем отправляется через электронную почту. Если документ не был изменен, то временный файл не требуется. будет отправлен исходный объект. `OnFileSendMail` загружает библиотека MAPI32. DLL, если она еще не загружена.

Специальная реализация `OnFileSendMail` для [коледокумент](../../mfc/reference/coledocument-class.md) обрабатывает составные файлы правильно.

`CDocument` поддерживает отправку документа по электронной почте, если имеется поддержка почты (MAPI). См. статьи, [посвященные MAPI](../../mfc/mapi.md) и [поддержку MAPI в MFC](../../mfc/mapi-support-in-mfc.md).

##  <a name="onloaddocumentfromstream"></a>CDocument:: Онлоаддокументфромстреам

Вызывается структурой при необходимости загрузки данных документа из потока.

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>Параметры

*пстреам*<br/>
Указатель на входящий поток.

*грфмоде*<br/>
Режим доступа к потоку.

### <a name="return-value"></a>Возвращаемое значение

S_OK, если загрузка прошла успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Remarks

##  <a name="onnewdocument"></a>CDocument:: Онневдокумент

Вызывается платформой как часть команды File New.

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ был успешно инициализирован; в противном случае — 0.

### <a name="remarks"></a>Remarks

Реализация по умолчанию этой функции вызывает функцию-член [делетеконтентс](#deletecontents) , чтобы убедиться, что документ пуст, а затем помечает новый документ как чистый. Переопределите эту функцию, чтобы инициализировать структуру данных для нового документа. Следует вызывать версию базового класса этой функции из переопределения.

Если пользователь выбирает команду файл New в приложении SDI, платформа использует эту функцию для повторной инициализации существующего документа вместо создания нового. Если пользователь выбирает файл New в приложении многодокументного интерфейса (MDI), платформа создает новый документ каждый раз, а затем вызывает эту функцию для ее инициализации. Код инициализации необходимо поместить в эту функцию, а не в конструктор, чтобы команда File New действовала в приложениях SDI.

Обратите внимание, что бывают случаи, когда `OnNewDocument` вызывается дважды. Это происходит, когда документ внедряется в качестве сервера документов ActiveX. Функция сначала вызывается методом `CreateInstance` (предоставленным классом, производным от `COleObjectFactory`), а второй раз — методом `InitNew` (предоставленным классом, производным от `COleServerDoc`).

### <a name="example"></a>Пример

В следующих примерах иллюстрируются альтернативные методы инициализации объекта Document.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

##  <a name="onopendocument"></a>CDocument:: OnOpenDocument

Вызывается платформой как часть команды открытия файла.

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*лпсзпаснаме*<br/>
Указывает путь к открытому документу.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ был успешно загружен; в противном случае — 0.

### <a name="remarks"></a>Remarks

Реализация этой функции по умолчанию открывает указанный файл, вызывает функцию-член [делетеконтентс](#deletecontents) , чтобы убедиться, что документ пуст, вызывает [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) для чтения содержимого файла, а затем помечает документ как чистый. Переопределите эту функцию, если хотите использовать нечто, отличное от механизма архива или механизма файла. Например, можно написать приложение, в котором документы представляют записи в базе данных, а не отдельные файлы.

Если пользователь выбирает команду Открыть файл в приложении SDI, платформа использует эту функцию для повторной инициализации существующего `CDocument` объекта вместо создания нового. Если пользователь выбирает файл, Открытый в приложении MDI, платформа создает новый объект `CDocument` каждый раз, а затем вызывает эту функцию для ее инициализации. Код инициализации необходимо поместить в эту функцию вместо в конструкторе, чтобы команда открытия файла действовала в приложениях SDI.

### <a name="example"></a>Пример

В следующих примерах иллюстрируются альтернативные методы инициализации объекта Document.

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

##  <a name="onpreviewhandlerqueryfocus"></a>CDocument:: Онпревиевхандлеркуерифокус

Направляет обработчик просмотра для возврата HWND, полученного из вызова функции `GetFocus`.

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>Параметры

*фвнд*<br/>
заполняет При возврате из этого метода содержит указатель на HWND, возвращенный из вызова функции `GetFocus` из основного потока обработчика просмотра.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха. или значение ошибки в противном случае.

### <a name="remarks"></a>Remarks

##  <a name="onpreviewhandlertranslateaccelerator"></a>CDocument:: Онпревиевхандлертранслатеакцелератор

Направляет обработчик просмотра для обработки нажатия клавиши, передаваемой из конвейера сообщений процесса, в котором выполняется обработчик просмотра.

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>Параметры

*пмсг*<br/>
окне Указатель на сообщение окна.

### <a name="return-value"></a>Возвращаемое значение

Если сообщение о нажатии клавиши может быть обработано обработчиком просмотра, обработчик обрабатывает его и возвращает S_OK. Если обработчик просмотра не может обработать сообщение с нажатием клавиши, он предлагает узлу через `IPreviewHandlerFrame::TranslateAccelerator`. Если узел обрабатывает сообщение, этот метод возвращает S_OK. Если узел не обрабатывает сообщение, этот метод возвращает S_FALSE.

### <a name="remarks"></a>Remarks

##  <a name="onrichpreviewbackcolorchanged"></a>CDocument:: Онричпревиевбаккколорчанжед

Вызывается при изменении цвета фона для расширенного просмотра.

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="onrichpreviewfontchanged"></a>CDocument:: Онричпревиевфонтчанжед

Вызывается при изменении шрифта с расширенным просмотром.

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="onrichpreviewsitechanged"></a>CDocument:: Онричпревиевситечанжед

Вызывается при изменении сайта с расширенным просмотром.

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="onrichpreviewtextcolorchanged"></a>CDocument:: Онричпревиевтекстколорчанжед

Вызывается, когда изменился цвет текста для расширенного просмотра.

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>Remarks

##  <a name="onsavedocument"></a>CDocument:: Онсаведокумент

Вызывается платформой как часть команды "сохранить файл" или "Сохранить как".

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*лпсзпаснаме*<br/>
Указывает полный путь, по которому должен быть сохранен файл.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если документ успешно сохранен; в противном случае — 0.

### <a name="remarks"></a>Remarks

Реализация по умолчанию этой функции открывает указанный файл, вызывает [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) для записи данных документа в файл, а затем помечает документ как чистый. Переопределите эту функцию, если требуется выполнить специальную обработку, когда платформа сохраняет документ. Например, можно написать приложение, в котором документы представляют записи в базе данных, а не отдельные файлы.

##  <a name="onunloadhandler"></a>CDocument:: Онунлоадхандлер

Вызывается платформой при выгрузке обработчика просмотра.

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>Remarks

##  <a name="onupdatefilesendmail"></a>CDocument:: Онупдатефилесендмаил

Включает команду ID_FILE_SEND_MAIL, если имеется поддержка почты (MAPI).

```
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*пкмдуи*<br/>
Указатель на объект [Поддержка CCmdUI](../../mfc/reference/ccmdui-class.md) , связанный с командой ID_FILE_SEND_MAIL.

### <a name="remarks"></a>Remarks

В противном случае функция удаляет команду ID_FILE_SEND_MAIL из меню, включая разделители выше или ниже пункта меню. MAPI включается, если библиотека MAPI32. DLL содержится в пути, а в разделе [mail] ВЫИГРЫШа. INI-файл, MAPI = 1. Большинство приложений помещают эту команду в меню файл.

`CDocument` поддерживает отправку документа по электронной почте, если имеется поддержка почты (MAPI). См. статьи, [посвященные MAPI](../../mfc/mapi.md) и [поддержку MAPI в MFC](../../mfc/mapi-support-in-mfc.md).

##  <a name="precloseframe"></a>CDocument::P Реклосефраме

Эта функция-член вызывается платформой до уничтожения окна фрейма.

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>Параметры

*пфраме*<br/>
Указатель на [CFrameWnd](../../mfc/reference/cframewnd-class.md) , содержащий связанный объект `CDocument`.

### <a name="remarks"></a>Remarks

Его можно переопределить, чтобы обеспечить пользовательскую очистку, но не забудьте также вызвать базовый класс.

По умолчанию `PreCloseFrame` не выполняет никаких действий в `CDocument`. Классы [коледокумент](../../mfc/reference/coledocument-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) , производные от `CDocument`, используют эту функцию-член.

##  <a name="readnextchunkvalue"></a>CDocument:: Реаднекстчунквалуе

Считывает следующее значение блока.

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>Параметры

*ппвалуе*<br/>
заполняет При возврате функции *ппвалуе* содержит значение, которое было считано.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

##  <a name="releasefile"></a>CDocument:: Релеасефиле

Эта функция-член вызывается платформой для освобождения файла и делает ее доступной для использования другими приложениями.

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>Параметры

*pFile*<br/>
Указатель на объект Кфиле, который нужно освободить.

*баборт*<br/>
Указывает, следует ли освободить файл с помощью `CFile::Close` или `CFile::Abort`. Значение FALSE, если файл должен быть освобожден с помощью [кфиле:: Close](../../mfc/reference/cfile-class.md#close); Значение TRUE, если файл должен быть освобожден с помощью [кфиле:: Abort](../../mfc/reference/cfile-class.md#abort).

### <a name="remarks"></a>Remarks

Если *баборт* имеет значение TRUE, `ReleaseFile` вызывает `CFile::Abort`, и файл освобождается. `CFile::Abort` не создаст исключение.

Если *баборт* имеет значение FALSE, `ReleaseFile` вызывает `CFile::Close` и файл освобождается.

Переопределите эту функцию-член, чтобы требовать действия от пользователя до освобождения файла.

##  <a name="removechunk"></a>CDocument:: Ремовечунк

Удаляет фрагмент с указанным GUID.

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>Параметры

*Guid*<br/>
Указывает идентификатор GUID удаляемого фрагмента.

*PID*<br/>
Указывает идентификатор процесса удаляемого фрагмента.

### <a name="remarks"></a>Remarks

##  <a name="removeview"></a>CDocument:: Ремовевиев

Вызовите эту функцию, чтобы отсоединить представление от документа.

```
void RemoveView(CView* pView);
```

### <a name="parameters"></a>Параметры

*pView*<br/>
Указывает на удаляемое представление.

### <a name="remarks"></a>Remarks

Эта функция удаляет указанное представление из списка представлений, связанных с документом. Он также задает для указателя документа представления значение NULL. Эта функция вызывается платформой при закрытом окне фрейма или при закрытии области окна-разделителя.

Вызывайте эту функцию только в том случае, если представление отсоединяется вручную. Как правило, вы разрешите платформе отключать документы и представления, определив объект [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) для связывания класса документа, класса представления и класс окна фрейма.

Пример реализации см. в примере на сайте [аддвиев](#addview) .

##  <a name="reportsaveloadexception"></a>CDocument:: Репортсавелоадексцептион

Вызывается, если возникает исключение (обычно это [кфиликсцептион](../../mfc/reference/cfileexception-class.md) или [карчивиксцептион](../../mfc/reference/carchiveexception-class.md)) при сохранении или загрузке документа.

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>Параметры

*лпсзпаснаме*<br/>
Указывает на имя сохраняемого или загружаемого документа.

*e*<br/>
Указывает на порождаемое исключение. Может иметь значение "NULL".

*бсавинг*<br/>
Флаг, указывающий, какая операция выполняется. ненулевое значение, если документ был сохранен, и 0, если документ был загружен.

*нидпдефаулт*<br/>
Идентификатор сообщения об ошибке, отображаемого, если функция не указывает более конкретного.

### <a name="remarks"></a>Remarks

Реализация по умолчанию проверяет объект исключения и ищет сообщение об ошибке, описывающее причину. Если конкретное сообщение не найдено или если *e* имеет значение null, используется общее сообщение, заданное параметром *нидпдефаулт* . Затем функция выводит окно сообщения с сообщением об ошибке. Переопределите эту функцию, если требуется предоставить дополнительные настраиваемые сообщения об ошибках. Это расширенный переопределяемый объект.

##  <a name="savemodified"></a>CDocument:: Савемодифиед

Вызвано структурой перед закрытием измененного документа.

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если продолжить и закрыть документ; 0, если документ не должен быть закрыт.

### <a name="remarks"></a>Remarks

Реализация этой функции по умолчанию отображает окно сообщения с вопросом, следует ли сохранять изменения в документе, если таковые были сделаны. Переопределите эту функцию, если программе требуется другая процедура запроса. Это расширенный переопределяемый объект.

##  <a name="setchunkvalue"></a>CDocument:: Сетчунквалуе

Задает значение фрагмента.

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Задает заданное значение фрагмента.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

##  <a name="setmodifiedflag"></a>CDocument:: SetModifiedFlag

Вызовите эту функцию после внесения изменений в документ.

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Параметры

*бмодифиед*<br/>
Флаг, указывающий, был ли изменен документ.

### <a name="remarks"></a>Remarks

Вызывая эту функцию согласованно, вы гарантируете, что платформа предложит пользователю сохранить изменения перед закрытием документа. Обычно для параметра *бмодифиед* следует использовать значение по умолчанию true. Чтобы пометить документ как чистый (неизмененный), вызовите эту функцию со значением FALSE.

##  <a name="setpathname"></a>CDocument:: Сетпаснаме

Вызовите эту функцию, чтобы указать полный путь к файлу документа на диске.

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Параметры

*лпсзпаснаме*<br/>
Указывает на строку, которая будет использоваться в качестве пути к документу.

*баддтомру*<br/>
Определяет, добавляется ли имя файла в список недавно использовавшихся файлов. Если задано значение TRUE, то имя файла добавляется; Если значение равно FALSE, он не добавляется.

### <a name="remarks"></a>Remarks

В зависимости от значения *баддтомру* добавляется или не добавляется путь к списку MRU, поддерживаемому приложением. Обратите внимание, что некоторые документы не связаны с файлом на диске. Вызывайте эту функцию только в том случае, если вы переопределяете реализацию по умолчанию для открытия и сохранения файлов, используемых платформой.

##  <a name="settitle"></a>CDocument:: Сеттитле

Вызовите эту функцию, чтобы указать заголовок документа (строку, отображаемую в заголовке окна фрейма).

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Параметры

*лпсзтитле*<br/>
Указывает на строку, которая будет использоваться в качестве заголовка документа.

### <a name="remarks"></a>Remarks

При вызове этой функции обновляются заголовки всех окон фрейма, в которых отображается документ.

##  <a name="updateallviews"></a>CDocument:: UpdateAllViews

Вызовите эту функцию после изменения документа.

```
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>Параметры

*псендер*<br/>
Указывает на представление, в котором изменен документ, или значение NULL, если все представления должны быть обновлены.

*лхинт*<br/>
Содержит сведения об изменении.

*финт*<br/>
Указывает объект, в котором хранятся сведения об изменении.

### <a name="remarks"></a>Remarks

Эту функцию следует вызывать после вызова функции члена [SetModifiedFlag](#setmodifiedflag) . Эта функция информирует каждое представление, присоединенное к документу, за исключением представления, заданного параметром *псендер*, что документ был изменен. Обычно эта функция вызывается из класса представления после того, как пользователь изменил документ через представление.

Эта функция вызывает функцию класса [CView:: OnUpdate](../../mfc/reference/cview-class.md#onupdate) для каждого из представлений документа, за исключением представления отправки, передав *финт* и *лхинт*. Используйте эти параметры для передачи сведений в представления об изменениях, внесенных в документ. Вы можете кодировать информацию с помощью *лхинт* и/или определить производный от [CObject](../../mfc/reference/cobject-class.md)класс, чтобы сохранить сведения об изменениях и передать объект этого класса с помощью *финт*. Переопределите функцию-член `CView::OnUpdate` в классе, производном от [CView](../../mfc/reference/cview-class.md), чтобы оптимизировать обновление отображения представления на основе переданных сведений.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>См. также раздел

[Пример МДИДОКВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример СНАПВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример НПП для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)
