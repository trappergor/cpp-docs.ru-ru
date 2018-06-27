---
title: CDocument-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e0d67012afe34cf3fe2c4633f2d838d1f3bfb49
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952535"
---
# <a name="cdocument-class"></a>CDocument-класс
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
|[CDocument::BeginReadChunks](#beginreadchunks)|Инициализирует фрагмента данных чтения.|  
|[CDocument::CanCloseFrame](#cancloseframe)|Расширенный overridable; Вызывается перед закрытием окна фрейма Просмотр этого документа.|  
|[CDocument::ClearChunkList](#clearchunklist)|Очищает список блоков.|  
|[CDocument::ClearPathName](#clearpathname)|Очищает путь объекта документа.|  
|[CDocument::DeleteContents](#deletecontents)|Вызывается для выполнения очистки документа.|  
|[CDocument::FindChunk](#findchunk)|Ищет блок с указанным идентификатором GUID.|  
|[CDocument::GetAdapter](#getadapter)|Возвращает указатель на объект, реализующий `IDocument` интерфейса.|  
|[CDocument::GetDocTemplate](#getdoctemplate)|Возвращает указатель на шаблон документа, который описывает тип документа.|  
|[CDocument::GetFile](#getfile)|Возвращает указатель на нужный `CFile` объекта.|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|Возвращает позицию первой в списке представления; используется для начала итерации.|  
|[CDocument::GetNextView](#getnextview)|Перебор элементов списка представлений, связанные с данным документом.|  
|[CDocument::GetPathName](#getpathname)|Возвращает путь к файлу данных документа.|  
|[CDocument::GetThumbnail](#getthumbnail)|Вызывается для создания растрового изображения, используемый поставщиком эскизов для отображения эскизов.|  
|[CDocument::GetTitle](#gettitle)|Возвращает название документа.|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Вызывается для инициализации содержимое поиска для обработчика поиска.|  
|[CDocument::IsModified](#ismodified)|Указывает, является ли документ был изменен с момента последнего сохранения.|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Сообщает ли этот экземпляр `CDocument` был создан объект для поиска и организовать обработчика.|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Вызывается, чтобы загрузить данные документа из потока.|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Вызывается перед изменением шрифта расширенного просмотра.|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|Вызывается после представление добавлены или удалены из документа.|  
|[CDocument::OnCloseDocument](#onclosedocument)|Вызывается, чтобы закрыть документ.|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Вызывается платформой, когда необходимо создать предварительный просмотр фрейм для расширенного просмотра.|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|Вызывается платформой в ответ на событие документа.|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|Переопределите этот метод в производном классе для рисования содержимого эскиз.|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|Вызывается платформой, когда необходимо загрузить данные документа из потока.|  
|[CDocument::OnNewDocument](#onnewdocument)|Вызывается, чтобы создать новый документ.|  
|[CDocument::OnOpenDocument](#onopendocument)|Вызывается, чтобы открыть существующий документ.|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|Направляет обработчика предварительного просмотра для возвращения из вызова функции при получении фокуса HWND.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Направляет обработчика предварительного просмотра для обработки нажатия клавиш, передаются из средства переноса сообщений процесса, в которой выполняется обработчик предварительного просмотра.|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Вызывается при изменении цвета фона расширенного просмотра.|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|Вызывается при изменении шрифта расширенного просмотра.|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|Вызывается при изменении расширенного просмотра узла.|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Вызывается при изменении цвета текста расширенного просмотра.|  
|[CDocument::OnSaveDocument](#onsavedocument)|Вызывается, чтобы сохранить документ на диске.|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|Вызывается платформой, когда выгружается обработчика предварительного просмотра.|  
|[CDocument::PreCloseFrame](#precloseframe)|Вызывается перед закрытием окна фрейма.|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Считывает значение следующего фрагмента данных.|  
|[CDocument::ReleaseFile](#releasefile)|Освобождает файл, чтобы сделать его доступным для использования другими приложениями.|  
|[CDocument::RemoveChunk](#removechunk)|Удаляет блок с указанным идентификатором GUID.|  
|[CDocument::RemoveView](#removeview)|Отсоединяет представления из документа.|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Расширенный overridable; вызывается, когда открытый или операция сохранения не может быть завершена из-за исключения.|  
|[CDocument::SaveModified](#savemodified)|Расширенный overridable; вызывается, чтобы запрашивать у пользователя, следует ли сохранить документ.|  
|[CDocument::SetChunkValue](#setchunkvalue)|Задает значение фрагмента данных.|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Задает флаг, указывающий, что документ были изменены с момента последнего сохранения.|  
|[CDocument::SetPathName](#setpathname)|Задает путь к файлу данных, используемый документом.|  
|[CDocument::SetTitle](#settitle)|Задает название документа.|  
|[CDocument::UpdateAllViews](#updateallviews)|Уведомляет все представления документа, был изменен.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDocument::OnFileSendMail](#onfilesendmail)|Отправляет сообщение электронной почты с присоединенным документом.|  
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|Включает команду Отправить почту, если присутствует почтовых служб.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Указывает, что `CDocument` объект был создан с dllhost для эскизов. Следует проверить `CView::OnDraw`.|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Указывает, что `CDocument` объект был создан с prevhost для `Rich Preview`. Следует проверить `CView::OnDraw`.|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|Указывает, что `CDocument` объект был создан индексатора или другие приложения поиска.|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Задает цвет фона окна расширенного просмотра. Этот цвет задан узлом.|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Указывает цвет окна расширенного просмотра. Этот цвет задан узлом.|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Задает шрифт текста для окна расширенного просмотра. Эти сведения шрифта задается узлом.|  
  
## <a name="remarks"></a>Примечания  
 Документ представляет собой единицу данных, пользователь обычно открывается с помощью команды открытия файла и сохраняется с помощью команды сохранения файла.  
  
 `CDocument` поддерживает стандартные операции, такие как создание документа, их загрузки и сохранения. Платформа манипулирует документы с помощью интерфейса определяются `CDocument`.  
  
 Приложение может поддерживать более чем один тип документа. Например приложение может поддерживать электронных таблиц и текстовых документов. Каждый тип документа имеет связанный документ шаблона; шаблон документа определяет, какие ресурсы (например, таблица значок, сочетания клавиш или меню), используемые для этого типа документа. Каждый документ содержит указатель на связанный с ним `CDocTemplate` объекта.  
  
 Пользователи взаимодействуют с документа с помощью [CView](../../mfc/reference/cview-class.md) объекты, связанные с ним. Представление Показ изображения в окне фрейма документа и интерпретирует как операций над документом ввод данных пользователем. Документ может иметь несколько представлений, связанные с ним. Когда пользователь открывает окно в документе, платформа создает представление и прикрепляет его к документу. Шаблон документа указывает, какой тип представлений и фреймов окна используются для отображения каждого типа документа.  
  
 Документы являются частью стандарта framework команды маршрутизации и в результате получает команды из компонентов стандартного пользовательского интерфейса (например, элемент меню сохранения файла). Документ откликается перенаправленных активное представление. Если документ не обрабатывает данной команды, он пересылает команду, чтобы шаблон документа, который управляет им.  
  
 При изменении данных документа, каждый из его представления должны отражать эти изменения. `CDocument` предоставляет [UpdateAllViews](#updateallviews) функция-член можно уведомить представления о таких изменениях, поэтому представления можно менять представление при необходимости. Платформа также предлагает пользователю сохранить измененный файл перед его закрытием.  
  
 Чтобы реализовать документы в типичном приложении, необходимо выполнить следующие задачи:  
  
-   Производный класс `CDocument` для каждого типа документа.  
  
-   Добавьте переменные-члены для хранения данных каждого документа.  
  
-   Реализация функции-члены для чтения и изменения данных документа. Представления документа отображаются наиболее важных пользователей этих функций-членов.  
  
-   Переопределить [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) функции-члена в классе документ для записи и чтения данных документа на диск и обратно.  
  
 `CDocument` Отправка документа по почте, если присутствует почтовых служб (MAPI) поддерживает. См. в статьях [MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).  
  
 Дополнительные сведения о `CDocument`, в разделе [сериализации](../../mfc/serialization-in-mfc.md), [разделы архитектуры Document/View](../../mfc/document-view-architecture.md), и [создание документов и представлений](../../mfc/document-view-creation.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="addview"></a>  CDocument::AddView  
 Эта функция вызывается для представления присоединить к документу.  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>Параметры  
 *pView*  
 Указывает добавляемый представления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция добавляет указанное представление списка представлений, связанные с данным документом; функция также устанавливает указатель представление документа в этот документ. Платформа вызывает эту функцию при присоединении объекта вновь созданное представление в документ. Это происходит в ответ на создание файла, открытие файла или новое окно команд или при разбиении окна-разделителя.  
  
 Эта функция вызывается только в том случае, если вы вручную создание и присоединение представления. Обычно позволит платформа подключения документов и представлений, определив [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объект, связанный класс документа, представления классов и класс окна фрейма.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="beginreadchunks"></a>  CDocument::BeginReadChunks  
 Инициализирует фрагмента данных чтения.  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="cancloseframe"></a>  CDocument::CanCloseFrame  
 Вызывается платформой перед закрытием окна фрейма отображение документа.  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Параметры  
 *pFrame*  
 Указывает на фрейм окна представления, прикрепленного к документу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если можно безопасно закрыть окно фрейма; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию проверяет наличие других фреймов, отображение документа. Если окно заданного фрейма последним, отображающий документ, данная функция предлагает пользователю сохранить документ в том случае, если он был изменен. Переопределите эту функцию, если вы хотите выполнять специальную обработку при закрытии окна фрейма. Существует расширенная overridable.  
  
##  <a name="cdocument"></a>  CDocument::CDocument  
 Создает **CDocument** объекта.  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа обрабатывает создание документов автоматически. Переопределить [OnNewDocument](#onnewdocument) функции-члена для выполнения инициализации на основе на уровне документа; это особенно важно в приложениях однооконный интерфейс (SDI).  
  
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
 Очистка путь от `CDocument` объекта позволяет приложению запрашивать у пользователя при сохранении документа в поле. Это делает **Сохранить** команда ведут себя как **Сохранить как** команды.  
  
##  <a name="deletecontents"></a>  CDocument::DeleteContents  
 Вызывается платформой для удаления данные документа без удаления **CDocument** сам объект.  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>Примечания  
 Он вызывается непосредственно перед документа будут уничтожены. Также называется убедитесь, что документ является пустым до повторного использования. Это особенно важно для приложения SDI, который использует только один документ; документ, повторно используется каждый раз, когда пользователь создает или открывает другой документ. Эта функция вызывается для реализации «Редактировать снимите все» или аналогичную команду, которая удаляет все данные документа. Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для удаления данных в документе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="findchunk"></a>  CDocument::FindChunk  
 Ищет блок с указанным идентификатором GUID.  
  
```  
virtual POSITION FindChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор GUID*  
 Указывает идентификатор GUID блока, для поиска.  
  
 *pid*  
 Указывает PID блока, для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Позиция в списке внутреннего блока в случае успешного выполнения. В противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getadapter"></a>  CDocument::GetAdapter  
 Возвращает указатель на объект, реализующий `IDocument` интерфейса.  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект, реализующий `IDocument` интерфейса.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="getdoctemplate"></a>  CDocument::GetDocTemplate  
 Эта функция вызывается для получения указателя шаблон документа для этого типа документа.  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на шаблон документа для этого типа документа или **NULL** Если документ не находится под управлением шаблон документа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="getfile"></a>  CDocument::GetFile  
 Вызовите эту функцию-член для получения указателя на `CFile` объекта.  
  
```  
virtual CFile* GetFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszFileName*  
 Строка, представляющая путь к нужному файлу. Путь может быть относительным или абсолютным.  
  
 *pError*  
 Указатель на объект исключения файлов, указывающее состояние завершения операции.  
  
 *nOpenFlags*  
 Для управления доступом и режимом доступа. Указывает действие, выполняемое при открытии файла. Можно комбинировать параметры, перечисленные в конструкторе CFile [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) с помощью побитового или (&#124;) оператор. Разрешения на доступ к одной и одной общей папки параметр являются обязательными; **modeCreate** и **modeNoInherit** режимы являются необязательными.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `CFile`.  
  
##  <a name="getfirstviewposition"></a>  CDocument::GetFirstViewPosition  
 Эта функция вызывается для получения позиции первое представление в списке представления, связанные с данным документом.  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации с [GetNextView](#getnextview) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getnextview"></a>  CDocument::GetNextView  
 Эта функция используется для просмотра всех представлениях документа.  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *rPosition*  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим вызовом `GetNextView` или [GetFirstViewPosition](#getfirstviewposition) функции-члены. Это значение не должно быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на представления, определяемому *rPosition*.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает представление определяется *rPosition* , а затем задает *rPosition* для **ПОЗИЦИИ** значение следующего представления в списке. Если полученный представление является последним в списке, затем *rPosition* равно **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="getpathname"></a>  CDocument::GetPathName  
 Вызывайте эту функцию, чтобы получить полный путь файла на диске документа.  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный путь к документу. Эта строка является пустой, если документ не был сохранен, либо не имеет связанных с ним файл на диске.  
  
##  <a name="getthumbnail"></a>  CDocument::GetThumbnail  
 Создает растровое изображение, чтобы использоваться поставщиком эскизов для отображения эскиза.  
  
```  
virtual BOOL GetThumbnail(
    UINT cx,  
    HBITMAP* phbmp,  
    DWORD* pdwAlpha);
```  
  
### <a name="parameters"></a>Параметры  
 *CX*  
 Задает ширину и высоту точечного рисунка.  
  
 *phbmp*  
 Содержит дескриптор растрового изображения, когда функция возвращает успешно.  
  
 *pdwAlpha*  
 Содержит DWORD, указав значение альфа-канала, когда функция возвращает успешно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если растровое изображение для эскиза был создан успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettitle"></a>  CDocument::GetTitle  
 Вызовите эту функцию для получения название документа, который обычно является производным от имени файла документа.  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Заголовок документа.  
  
##  <a name="initializesearchcontent"></a>  CDocument::InitializeSearchContent  
 Вызывается для инициализации содержимое поиска для обработчика поиска.  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе для инициализации поиска содержимого. Содержимое должно быть строкой с частей, разделенных «;». Например «точки; прямоугольник; элемент OLE».  
  
##  <a name="ismodified"></a>  CDocument::IsModified  
 Эта функция вызывается для определения, является ли документ был изменен с момента последнего сохранения.  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ был изменен с момента последнего сохранения; в противном случае — 0.  
  
##  <a name="issearchandorganizehandler"></a>  CDocument::IsSearchAndOrganizeHandler  
 Сообщает ли этот экземпляр `CDocument` был создан для обработчика поиска & организация.  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если этот экземпляр `CDocument` был создан для обработчика поиска & организация.  
  
### <a name="remarks"></a>Примечания  
 В настоящее время эта функция возвращает `TRUE` только для расширенного просмотра обработчиками, реализованными в развертывании сервера обработки. Можно задать соответствующие флаги (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) на уровень приложения, чтобы эта функция возвращаемого `TRUE`.  
  
##  <a name="loaddocumentfromstream"></a>  CDocument::LoadDocumentFromStream  
 Вызывается для загрузки данных документа из потока.  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>Параметры  
 *pStream*  
 Указатель на поток. Этот поток является результатом оболочки.  
  
 *dwGrfMode*  
 Режим доступа к потоку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция загрузки выполнена успешно, в противном случае значение HRESULT с кодом ошибки.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить этот метод в производном классе, чтобы настроить способ загрузки данных из потока.  
  
##  <a name="m_bgetthumbnailmode"></a>  CDocument::m_bGetThumbnailMode  
 Указывает, что `CDocument` объект был создан с dllhost для эскизов. Следует проверить `CView::OnDraw`.  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>Примечания  
 `TRUE` Указывает, был создан документ dllhost для эскизов.  
  
##  <a name="m_bpreviewhandlermode"></a>  CDocument::m_bPreviewHandlerMode  
 Указывает, что `CDocument` объект был создан с prevhost для расширенного просмотра. Следует проверить `CView::OnDraw`.  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>Примечания  
 `TRUE` Указывает, что документ был создан с prevhost для расширенного просмотра.  
  
##  <a name="m_bsearchmode"></a>  CDocument::m_bSearchMode  
 Указывает, что `CDocument` индексатором или другим приложением поиска был создан объект.  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>Примечания  
 `TRUE` Указывает, что документ был создан, индексатор или другое приложение для поиска.  
  
##  <a name="m_clrrichpreviewbackcolor"></a>  CDocument::m_clrRichPreviewBackColor  
 Задает цвет фона окна расширенного просмотра. Этот цвет задан узлом.  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_clrrichpreviewtextcolor"></a>  CDocument::m_clrRichPreviewTextColor  
 Указывает цвет окна расширенного просмотра. Этот цвет задан узлом.  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_lfrichpreviewfont"></a>  CDocument::m_lfRichPreviewFont  
 Задает шрифт для окна расширенного просмотра. Эти сведения шрифта задается узлом.  
  
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
 Вызывается структурой после представление добавлены или удалены из документа.  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция проверяет ли последнее представление удаляется и, если это так, удаляет документа. Переопределите эту функцию, если вы хотите выполнять специальную обработку, когда платформа добавляет или удаляет представления. Например документ, чтобы оставаться открытым, даже в том случае, если нет, присоединенные к ней представлений следует переопределите эту функцию.  
  
##  <a name="onclosedocument"></a>  CDocument::OnCloseDocument  
 Вызывается платформой при закрытии документа, обычно во время выполнения команды File Close.  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция удаляет все кадры, используется для просмотра документа, закрывает представление, очищает содержимое документа и затем вызывает метод [DeleteContents](#deletecontents) функции-члена удалить документ данные.  
  
 Переопределите эту функцию, если требуется выполнять обработку специальные операции очистки, когда платформа закрывает документ. Например документ представляет собой запись в базе данных, можно переопределить эту функцию, чтобы закрыть базу данных. Версия этой функции базового класса следует вызывать из переопределения.  
  
##  <a name="oncreatepreviewframe"></a>  CDocument::OnCreatePreviewFrame  
 Вызывается платформой, когда необходимо создать предварительный просмотр фрейм для расширенного просмотра.  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если кадр создан успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="ondocumentevent"></a>  CDocument::OnDocumentEvent  
 Вызывается платформой в ответ на событие документа.  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *deEvent*  
 Перечисляемого типа данных, описывающий тип события.  
  
### <a name="remarks"></a>Примечания  
 События документа может повлиять на несколько классов. Этот метод отвечает за обработку события документа, не влияющие на классы [CDocument-класс](../../mfc/reference/cdocument-class.md). В настоящее время является единственным классом, должен отвечать на события документа [CDataRecoveryHandler класса](../../mfc/reference/cdatarecoveryhandler-class.md). `CDocument` Класс имеет другие переопределяемые методы, отвечающий за обработку эффект на `CDocument`.  
  
 В следующей таблице перечислены возможные значения для *deEvent* и события, которые они соответствуют.  
  
|Значение|Соответствующее событие|  
|-----------|-------------------------|  
|`onAfterNewDocument`|Был создан новый документ.|  
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
 *dc*  
 Ссылка на контекст устройства.  
  
 *lprcBounds*  
 Указывает ограничивающий прямоугольник области, где должен отображаться эскиз.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onfilesendmail"></a>  CDocument::OnFileSendMail  
 Отправляет сообщение через узел резидентного почтового (если таковые имеются) в документе как вложение.  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>Примечания  
 `OnFileSendMail` вызовы [OnSaveDocument](#onsavedocument) для сериализации (Сохранить) без имени и измененные документы во временный файл, который затем отправляется по электронной почте. Если документ не был изменен, временный файл не требуется; отправляется исходный. `OnFileSendMail` Загружает MAPI32. Библиотеки DLL, если он еще не загружена.  
  
 Специальные реализация `OnFileSendMail` для [COleDocument](../../mfc/reference/coledocument-class.md) дескрипторы составные файлы правильно.  
  
 **CDocument** поддерживает отправку документа по почте, если присутствует почтовых служб (MAPI). См. в статьях [разделы MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="onloaddocumentfromstream"></a>  CDocument::OnLoadDocumentFromStream  
 Вызывается платформой, когда необходимо загрузить данные документа из потока.  
  
```  
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,  
    DWORD grfMode);
```  
  
### <a name="parameters"></a>Параметры  
 *pStream*  
 Указатель на поток входящих.  
  
 *grfMode*  
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
 Ненулевое значение, если документ был успешно инициализирован; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция вызывает [DeleteContents](#deletecontents) убедитесь, что документ является пустым и пометит новый документ как чистая функция-член. Переопределите эту функцию для инициализации структуры данных для нового документа. Версия этой функции базового класса следует вызывать из переопределения.  
  
 При выборе команды создания файла в приложении SDI платформа использует эту функцию для повторной инициализации существующих документов, а не создавать новый. Если пользователь выбирает новый файл в приложении несколько интерфейса (MDI) документа, платформа создает новый документ и затем вызывает эту функцию для инициализации. В этой функции, а не в конструкторе для команды создания файла для эффективного SDI-приложения, необходимо поместить код инициализации.  
  
 Обратите внимание, что существуют ситуации, когда `OnNewDocument` вызывается дважды. Это происходит, когда документ внедряется в виде сервером ActiveX. Сначала вызывается функция `CreateInstance` метод (предоставляемые `COleObjectFactory`-производного класса) и второй раз, `InitNew` метод (предоставляемые `COleServerDoc`-производного класса).  
  
### <a name="example"></a>Пример  
 В следующих примерах показаны альтернативные методы инициализации объекта документа.  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="onopendocument"></a>  CDocument::OnOpenDocument  
 Вызывается платформой как часть команды открытия файла.  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPathName*  
 Указывает путь для открываемого документа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ был успешно загружен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция открывает указанный файл, вызовы [DeleteContents](#deletecontents) убедитесь, что документ является пустым, функция-член вызывает [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) на чтение этого файла содержимое, а затем помечается как очистить. Переопределите эту функцию, если вы хотите использовать имя, отличное от механизма архива или механизм файла. Например можно написать приложение, где документы представляют записей в базе данных, а не отдельные файлы.  
  
 При выборе команды Открыть файл в приложении SDI платформа использует эту функцию для повторной инициализации существующих **CDocument** объекта, а не создавать новый. Если пользователь выберет открытие файла в приложении MDI, платформа создает новое **CDocument** объект каждый раз, а затем вызывает эту функцию для инициализации. В этой функции, а не в конструкторе для команды открытия файла для эффективного SDI-приложения, необходимо поместить код инициализации.  
  
### <a name="example"></a>Пример  
 В следующих примерах показаны альтернативные методы инициализации объекта документа.  
  
 [!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="onpreviewhandlerqueryfocus"></a>  CDocument::OnPreviewHandlerQueryFocus  
 Направляет обработчика предварительного просмотра для возврата HWND получены из вызова метода `GetFocus` функции.  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>Параметры  
 *phwnd*  
 [out] По возвращении из этого метода содержит указатель на HWND, возвращаемый вызовом `GetFocus` функции из обработчика предварительного просмотра основного потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если успешно; или, в противном случае — значение ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onpreviewhandlertranslateaccelerator"></a>  CDocument::OnPreviewHandlerTranslateAccelerator  
 Направляет обработчика предварительного просмотра для обработки нажатия клавиш, передаются из средства переноса сообщений процесса, в которой выполняется обработчик предварительного просмотра.  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>Параметры  
 *pmsg*  
 [in] Указатель на окно сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если нажатие клавиши сообщения могут обрабатываться обработчика предварительного просмотра, обработчик обрабатывает его и возвращает значение S_OK. Если обработчик предварительного просмотра не удается обработать сообщение нажатие клавиши, он предлагает до узла через `IPreviewHandlerFrame::TranslateAccelerator`. Если узел обрабатывает сообщение, этот метод возвращает значение S_OK. Если узел не обрабатывает сообщение, этот метод возвращает значение S_FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onrichpreviewbackcolorchanged"></a>  CDocument::OnRichPreviewBackColorChanged  
 Вызывается при изменении цвета фона расширенного просмотра.  
  
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
 Вызывается при изменении расширенного просмотра узла.  
  
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
 Вызывается платформой как часть команды "Сохранить файл" или "Сохранить как.  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPathName*  
 Указывает полный путь для сохранения файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ был успешно сохранен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция открывает указанный файл, вызовы [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для записи данных документа в файл, а затем метки документа как очистить. Переопределите эту функцию, если вы хотите выполнять специальную обработку, когда платформа сохраняет документ. Например можно написать приложение, где документы представляют записей в базе данных, а не отдельные файлы.  
  
##  <a name="onunloadhandler"></a>  CDocument::OnUnloadHandler  
 Вызывается платформой при выгрузке обработчика предварительного просмотра.  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onupdatefilesendmail"></a>  CDocument::OnUpdateFileSendMail  
 Включает **ID_FILE_SEND_MAIL** команды, если имеется поддержка почты (MAPI).  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 *pCmdUI*  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объекта, связанного с **ID_FILE_SEND_MAIL** команды.  
  
### <a name="remarks"></a>Примечания  
 В противном случае эта функция удаляет **ID_FILE_SEND_MAIL** команды меню, включая разделители выше или ниже меню элемента в соответствии. MAPI доступен в том случае, если MAPI32. DLL отсутствует в пути и в разделе [почты] WIN. INI-файл, MAPI = 1. Большинство приложений поместите эту команду в меню «файл».  
  
 **CDocument** поддерживает отправку документа по почте, если присутствует почтовых служб (MAPI). См. в статьях [разделы MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="precloseframe"></a>  CDocument::PreCloseFrame  
 Эта функция-член вызывается платформой, до уничтожения окна фрейма.  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Параметры  
 *pFrame*  
 Указатель на [CFrameWnd](../../mfc/reference/cframewnd-class.md) , содержащий связанный `CDocument` объекта.  
  
### <a name="remarks"></a>Примечания  
 Его можно переопределить, чтобы предоставить пользовательскую очистку, но необходимо вызвать метод базового класса также.  
  
 Значение по умолчанию для `PreCloseFrame` не выполняет никаких действий `CDocument`. `CDocument`-Производные классы [COleDocument](../../mfc/reference/coledocument-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) использовать эту функцию-член.  
  
##  <a name="readnextchunkvalue"></a>  CDocument::ReadNextChunkValue  
 Считывает значение следующего фрагмента данных.  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>Параметры  
 *ppValue*  
 [out] Если функция возвращает, *ppValue* содержит значение, которое было прочитано.  
  
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
 *pFile*  
 Указатель на объект CFile снятия.  
  
 *bAbort*  
 Указывает, является ли файл снятия с помощью `CFile::Close` или `CFile::Abort`. **FALSE** если он освобождается с помощью [CFile::Close](../../mfc/reference/cfile-class.md#close); **TRUE** если он освобождается с помощью [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="remarks"></a>Примечания  
 Если *bAbort* — **TRUE**, `ReleaseFile` вызовы `CFile::Abort`, и файл освобождается. `CFile::Abort` не вызовет исключение.  
  
 Если *bAbort* — **FALSE**, `ReleaseFile` вызовы `CFile::Close` и файл освобождается.  
  
 Переопределите эту функцию-член требовать вмешательства пользователя до освобождения файла.  
  
##  <a name="removechunk"></a>  CDocument::RemoveChunk  
 Удаляет блок с указанным идентификатором GUID.  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Параметры  
 *Guid*  
 Указывает идентификатор GUID удаляемого блока.  
  
 *Идентификатор процесса*  
 Указывает идентификатор Процесса блока, должны быть удалены.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removeview"></a>  CDocument::RemoveView  
 Эта функция вызывается для отсоединения представления из документа.  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>Параметры  
 *pView*  
 Указывает представление удаления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция удаляет указанное представление из списка представлений, связанные с данным документом; Этот параметр также устанавливает указатель представления документа **NULL**. Эта функция вызывается платформой при закрытии окна фрейма или при закрытии панели окна-разделителя.  
  
 Эта функция вызывается только в том случае, если вручную отсоединение представления. Обычно позволит платформа отсоединения документов и представлений, определив [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объект, связанный класс документа, представления классов и класс окна фрейма.  
  
 Можно найти в [AddView](#addview) пример реализации интерфейса.  
  
##  <a name="reportsaveloadexception"></a>  CDocument::ReportSaveLoadException  
 Вызывается, если исключение (обычно [CFileException](../../mfc/reference/cfileexception-class.md) или [CArchiveException](../../mfc/reference/carchiveexception-class.md)) во время сохранения или загрузки документа.  
  
```  
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,  
    CException* e,  
    BOOL bSaving,  
    UINT nIDPDefault);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPathName*  
 Указывает имя документа, которая находится в процессе сохранения или загрузки.  
  
 *e*  
 Указывает исключение, вызванное исключение. Возможно, **NULL**.  
  
 *bSaving*  
 Флаг, указывающий, какая операция была выполняется; ненулевое значение, если документ был были сохранены, 0, если при загрузке документа.  
  
 *nIDPDefault*  
 Идентификатор сообщения об ошибке будет отображаться, если функция не указать более одну из них.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию проверяет объекта исключения и ищет сообщение об ошибке, в частности, описывающее причину. Если сообщение не найден или *e* — **NULL**, общие сообщения, заданного *nIDPDefault* параметр используется. Функция затем отображает окно сообщения, содержащее сообщение об ошибке. Переопределите эту функцию, если вы хотите предоставить дополнительные, настраиваемых сообщений. Существует расширенная overridable.  
  
##  <a name="savemodified"></a>  CDocument::SaveModified  
 Вызывается платформой перед измененный документ будет закрыт.  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если можно безопасно продолжить и закрыть документ; 0, если документ не был закрыт.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция отображает окно сообщения с запросом пользователя, следует ли сохранить изменения в документе, если они были внесены. Переопределите эту функцию, если программа требует другой процедуры запроса. Существует расширенная overridable.  
  
##  <a name="setchunkvalue"></a>  CDocument::SetChunkValue  
 Задает значение фрагмента данных.  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Параметры  
 *pValue*  
 Указывает значение фрагмента данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setmodifiedflag"></a>  CDocument::SetModifiedFlag  
 Эта функция вызывается после внесения изменения в документе.  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *bModified*  
 Флаг, указывающий, был ли изменен документ.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции постоянно, убедитесь, что платформа предлагает пользователю сохранить изменения перед закрытием документа. Обычно следует использовать значение по умолчанию **TRUE** для *bModified* параметра. Чтобы пометить документ как очистить (без изменений), вызовите эту функцию со значением **FALSE**.  
  
##  <a name="setpathname"></a>  CDocument::SetPathName  
 Эта функция вызывается для укажите полный путь к файлу документа на диске.  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPathName*  
 Указывает строку для использования в качестве пути для документа.  
  
 *bAddToMRU*  
 Определяет, является ли имя файла добавляется в список последних использовавшихся списка файлов (MRU). Если **задано значение TRUE,** добавляется имя файла; если **FALSE**, он не добавляется.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от значения *bAddToMRU* добавляется путь, или не добавлен в список последних выбиравшихся файлов поддерживается приложением. Обратите внимание, что некоторые документы не связаны с файла на диске. Эта функция вызывается только в том случае, если выполняется переопределение реализация по умолчанию для открытия и сохранения файлов, используемых платформой.  
  
##  <a name="settitle"></a>  CDocument::SetTitle  
 Вызывайте эту функцию, чтобы указать название документа (строку, отображаемую в строке заголовка окна фрейма).  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszTitle*  
 Указывает строку для использования в качестве название документа.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции обновляет названия всех фреймов, отобразить документ.  
  
##  <a name="updateallviews"></a>  CDocument::UpdateAllViews  
 Эта функция вызывается после изменения документа.  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pSender*  
 Указывает представление, которое изменение в документ или **NULL** Если все представления должны быть обновлены.  
  
 *lHint*  
 Содержит сведения об изменении.  
  
 *pHint*  
 Указывает на объект хранения информации об изменении.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию следует вызывать после вызова метода [SetModifiedFlag](#setmodifiedflag) функции-члена. Эта функция сообщает каждого представления, прикрепленного к документу, за исключением представление, определяемое *pSender*, что изменения документа. Обычно эта функция вызывается из представления класса после изменения документа через представление.  
  
 Эта функция вызывает [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) просмотреть функция-член для каждого из представлений документов, за исключением отправку, передавая *pHint* и *lHint*. Используйте эти параметры для передачи информации об изменениях, внесенных в документ с представлениями. Можно закодировать с помощью сведения *lHint* и/или можно определить [CObject](../../mfc/reference/cobject-class.md)-производный класс для хранения информации об изменениях и передать объект этого класса с помощью *pHint*. Переопределить `CView::OnUpdate` функции-члена в вашей [CView](../../mfc/reference/cview-class.md)-производный класс для оптимизации обновление отображения представления на основе переданного сведений.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDIDOCVW](../../visual-cpp-samples.md)   
 [Пример MFC: SNAPVW](../../visual-cpp-samples.md)   
 [Пример MFC NPP](../../visual-cpp-samples.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)
