---
title: "CDocument-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocument
dev_langs:
- C++
helpviewer_keywords:
- documents [C++], serialization
- files [C++], documents
- command handling, documents and
- documents [C++], document classes
- documents [C++], multiple views
- serialization [C++], documents and
- CDocument class
- command routing, documents and
- views [C++], document
- documents [C++], command routing
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4d64b95f77139d984b855e710f3951434e489dd5
ms.lasthandoff: 02/24/2017

---
# <a name="cdocument-class"></a>CDocument-класс
Предоставляет базовую функциональность для определяемых пользователем классов документа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocument : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocument::CDocument](#cdocument)|Создает объект `CDocument`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocument::AddView](#addview)|Присоединяет представление документа.|  
|[CDocument::BeginReadChunks](#beginreadchunks)|Инициализирует блок чтения.|  
|[CDocument::CanCloseFrame](#cancloseframe)|Дополнительно overridable; Вызывается перед закрытием окна фрейма, просмотр этого документа.|  
|[CDocument::ClearChunkList](#clearchunklist)|Очищает список блоков.|  
|[CDocument::ClearPathName](#clearpathname)|Очищает путь объекта документа.|  
|[CDocument::DeleteContents](#deletecontents)|Вызывается для выполнения очистки документа.|  
|[CDocument::FindChunk](#findchunk)|Ищет фрагмент данных с указанным идентификатором GUID.|  
|[CDocument::GetAdapter](#getadapter)|Возвращает указатель на объект, реализующий `IDocument` интерфейса.|  
|[CDocument::GetDocTemplate](#getdoctemplate)|Возвращает указатель на шаблон документа, который описывает тип документа.|  
|[CDocument::GetFile](#getfile)|Возвращает указатель на нужный `CFile` объекта.|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|Возвращает позицию первой в списке представления; используется для начала итерации.|  
|[CDocument::GetNextView](#getnextview)|Перебор списка представлений, связанные с данным документом.|  
|[CDocument::GetPathName](#getpathname)|Возвращает путь к файлу данных документа.|  
|[CDocument::GetThumbnail](#getthumbnail)|Вызывается для создания растрового изображения для использования поставщика уменьшенных изображений для отображения эскиза.|  
|[CDocument::GetTitle](#gettitle)|Возвращает заголовок документа.|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Вызывается для инициализации поиск содержимого для поиска обработчика.|  
|[CDocument::IsModified](#ismodified)|Указывает ли документ был изменен с момента последнего сохранения.|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Сообщает ли этот экземпляр `CDocument` был создан объект для поиска & организовать обработчика.|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Вызывается, чтобы загрузить данные документа из потока.|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Вызывается перед изменением шрифта расширенного просмотра.|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|Вызывается после представления добавлен или удален из документа.|  
|[CDocument::OnCloseDocument](#onclosedocument)|Вызывается, чтобы закрыть документ.|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Вызывается платформой, когда он должен создать рамки предварительной версии для расширенного просмотра.|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|Вызывается средой в ответ на событие документа.|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|Переопределите этот метод в производном классе для рисования содержимого эскиза.|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|Вызывается платформой, когда это необходимо загрузить данные документа из потока.|  
|[CDocument::OnNewDocument](#onnewdocument)|Вызывается для создания нового документа.|  
|[CDocument::OnOpenDocument](#onopendocument)|Вызывается для открытия существующего документа.|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|Указывает обработчик просмотра для возвращения из вызова функции при получении фокуса HWND.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Указывает обработчик просмотра для обработки нажатия клавиш, передаются из средства переноса сообщений процесса, в котором выполняется обработчик просмотра.|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Вызывается при изменении цвета фона расширенного просмотра.|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|Вызывается при изменении шрифта расширенного просмотра.|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|Вызывается при изменении расширенного просмотра сайта.|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Вызывается при изменении цвета текста расширенного просмотра.|  
|[CDocument::OnSaveDocument](#onsavedocument)|Вызывается, чтобы сохранить документ на диске.|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|Вызывается инфраструктурой при выгрузке обработчика просмотра.|  
|[CDocument::PreCloseFrame](#precloseframe)|Вызывается перед закрытием окна фрейма.|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Считывает следующее значение фрагмента данных.|  
|[CDocument::ReleaseFile](#releasefile)|Освобождает файл, чтобы сделать его доступным для использования другими приложениями.|  
|[CDocument::RemoveChunk](#removechunk)|Удаляет фрагмент данных с указанным идентификатором GUID.|  
|[CDocument::RemoveView](#removeview)|Отсоединяет представления из документа.|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Дополнительно overridable; вызывается, когда открытый или операция сохранения не может быть завершена из-за исключения.|  
|[CDocument::SaveModified](#savemodified)|Дополнительно overridable; вызывается, чтобы запрашивать у пользователя, следует ли сохранить документ.|  
|[CDocument::SetChunkValue](#setchunkvalue)|Задает значение фрагмента данных.|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Задает флаг, указывающий, что документ были изменены с момента последнего сохранения.|  
|[CDocument::SetPathName](#setpathname)|Задает путь к файлу данных, используемый документом.|  
|[CDocument::SetTitle](#settitle)|Задает заголовок документа.|  
|[CDocument::UpdateAllViews](#updateallviews)|Уведомляет все представления документа, был изменен.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocument::OnFileSendMail](#onfilesendmail)|Отправляет сообщение электронной почты с вложенным документом.|  
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|Включает команду Отправить почту при наличии почтовых служб.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Указывает, что `CDocument` объект был создан с dllhost для эскизов. Следует проверить `CView::OnDraw`.|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Указывает, что `CDocument` объект был создан с prevhost для `Rich Preview`. Следует проверить `CView::OnDraw`.|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|Указывает, что `CDocument` был создан объект, индексатора или другого приложения поиска.|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Задает цвет фона окна расширенного просмотра. Этот цвет задан узлом.|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Задает основной цвет окна расширенного просмотра. Этот цвет задан узлом.|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Задает шрифт для окна расширенного просмотра. Эта информация шрифт задается узлом.|  
  
## <a name="remarks"></a>Примечания  
 Документ представляет единицу данных, пользователь обычно открывается с помощью команды «Открыть файл» и сохраняется с помощью команды сохранения файла.  
  
 **CDocument** поддерживает стандартные операции, такие как создание документа, их загрузки и сохранения. Платформа framework управляет документами с помощью интерфейса, определенного **CDocument**.  
  
 Приложение может поддерживать более одного типа документа. Например приложение может поддерживать электронных таблиц и текстовых документов. Каждый тип документа имеет связанный документ шаблона; шаблон документа определяет, какие ресурсы (например, сочетания клавиш, значок или меню таблицы) используются для этого типа документа. Каждый документ содержит указатель на связанный с ним `CDocTemplate` объекта.  
  
 Пользователи взаимодействуют с документа с помощью [CView](../../mfc/reference/cview-class.md) объекты, связанные с ним. Представление отображает изображение в окне фрейма документа и интерпретирует входные данные пользователя как операций над документом. Документ может иметь несколько представлений, связанных с ним. Когда пользователь открывает окно документа, платформа создает представление и присоединяет его к документу. Шаблон документа указывает, какой тип представления и рамка окна используются для отображения каждого типа документа.  
  
 Документы являются частью стандарта framework команды маршрутизации и таким образом получать команды от компонентов стандартного пользовательского интерфейса (например, элемент меню сохранения файла). Документ откликается пересылаемый активное представление. Если документ не обрабатывает данной команды, она передает команду, чтобы шаблон документа, который управляет им.  
  
 При изменении данных документа, каждый из его представлений должны отражать эти изменения. **CDocument** предоставляет [UpdateAllViews](#updateallviews) функции-члена для вас для уведомления представления о таких изменениях, поэтому представления можно менять представление при необходимости. Платформа также предлагает пользователю сохранить измененный файл перед его закрытием.  
  
 Для реализации документы в типичном приложении, выполните следующие действия.  
  
-   Производный класс от **CDocument** для каждого типа документа.  
  
-   Добавьте переменные-члены для хранения данных каждого документа.  
  
-   Реализация функции-члены для чтения и изменения данных документа. Представления документа — это наиболее важных пользователи этих функций-членов.  
  
-   Переопределение [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) функции-члена в классе документ для записи и чтения данных документа и с диска.  
  
 **CDocument** поддерживает отправку документа электронной почте при наличии поддержки электронной почты (MAPI). См. в статьях [MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).  
  
 Дополнительные сведения о **CDocument**, в разделе [сериализации](../../mfc/serialization-in-mfc.md), [разделы архитектуры документ/представление](../../mfc/document-view-architecture.md), и [создания документов и представлений](../../mfc/document-view-creation.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-nameaddviewa--cdocumentaddview"></a><a name="addview"></a>CDocument::AddView  
 Эта функция вызывается для присоединения представления в документ.  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>Параметры  
 `pView`  
 Указывает добавляемый представления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция добавляет указанное представление списка представлений, связанные с данным документом; функция также задает указатель представление документа в этом документе. Платформа вызывает эту функцию при присоединении объекта вновь созданное представление в документ. Это происходит в ответ на команду новый файл, откройте файл или окно или при разбиении окна-разделителя.  
  
 Эта функция вызывается только в том случае, если вы вручную создание и присоединение представления. Обычно позволит платформа подключения документов и представлений, определив [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) для привязки класса документов, представления класса и класс фреймового окна.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocViewSDI&#12;](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="a-namebeginreadchunksa--cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>CDocument::BeginReadChunks  
 Инициализирует блок чтения.  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namecancloseframea--cdocumentcancloseframe"></a><a name="cancloseframe"></a>CDocument::CanCloseFrame  
 Вызывается средой перед закрытием окна фрейма, отображение документа.  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Параметры  
 `pFrame`  
 Точки в фрейме окна представления, прикрепленной к документу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если можно безопасно закрыть окна фрейма. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию проверяет наличие других окна фрейма документа. Если окно заданного фрейма последний отображает документ, данная функция предлагает пользователю сохранить документ, если он был изменен. Переопределите эту функцию, если вы хотите выполнять специальную обработку при закрытии окна фрейма. Существует расширенная переопределяемыми.  
  
##  <a name="a-namecdocumenta--cdocumentcdocument"></a><a name="cdocument"></a>CDocument::CDocument  
 Создает **CDocument** объекта.  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>Примечания  
 Платформа framework обрабатывает создание документов для вас. Переопределение [OnNewDocument](#onnewdocument) функции-члена для выполнения инициализации на основе каждого документа; это особенно важно в приложениях однооконный интерфейс (SDI).  
  
##  <a name="a-nameclearchunklista--cdocumentclearchunklist"></a><a name="clearchunklist"></a>CDocument::ClearChunkList  
 Очищает список блоков.  
  
```  
virtual void ClearChunkList ();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameclearpathnamea--cdocumentclearpathname"></a><a name="clearpathname"></a>CDocument::ClearPathName  
 Очищает путь объекта документа.  
  
```  
virtual void ClearPathName();
```  
  
### <a name="remarks"></a>Примечания  
 Очистка путь от `CDocument` объекта позволяет приложению запрашивать пользователя, если затем сохранить документ. Это делает **Сохранить** команда ведут себя как **Сохранить как** команды.  
  
##  <a name="a-namedeletecontentsa--cdocumentdeletecontents"></a><a name="deletecontents"></a>CDocument::DeleteContents  
 Вызывается платформой для удаления данных документов без потери **CDocument** сам объект.  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>Примечания  
 Он вызывается непосредственно перед документа будут уничтожены. Также называется обеспечивают пустой документ до повторного использования. Это особенно важно для приложения SDI, который использует только один документ; документ используется повторно всякий раз, когда пользователь создает или открывает другой документ. Эта функция вызывается для реализации «Правка-очистить все» или похожей командой, которая удаляет все данные документа. Реализация по умолчанию этой функции не выполняет никаких действий. Переопределите эту функцию для удаления данных в документе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#57;](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="a-namefindchunka--cdocumentfindchunk"></a><a name="findchunk"></a>CDocument::FindChunk  
 Ищет фрагмент данных с указанным идентификатором GUID.  
  
```  
virtual POSITION FindChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Параметры  
 `guid`  
 Задает идентификатор GUID блока для поиска.  
  
 `pid`  
 Указывает PID блока для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Позиция в списке внутреннего блока в случае успешного выполнения. В противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetadaptera--cdocumentgetadapter"></a><a name="getadapter"></a>CDocument::GetAdapter  
 Возвращает указатель на объект, реализующий `IDocument` интерфейса.  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект, реализующий `IDocument` интерфейса.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetdoctemplatea--cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>CDocument::GetDocTemplate  
 Эта функция вызывается для получения указателя на шаблон документов для данного типа документа.  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на шаблон документа для этого типа документа или **NULL** Если документ не управляется шаблон документа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#58;](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="a-namegetfilea--cdocumentgetfile"></a><a name="getfile"></a>CDocument::GetFile  
 Вызов этой функции-члена для получения указателя на `CFile` объект.  
  
```  
virtual CFile* GetFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszFileName`  
 Строка, представляющая путь к нужному файлу. Путь может быть относительным или абсолютным.  
  
 `pError`  
 Указатель на объект исключения файлов, указывающее состояние завершения операции.  
  
 `nOpenFlags`  
 Совместное использование и режимом доступа. Указывает действие, выполняемое при открытии файла. Можно комбинировать параметры, перечисленные в конструкторе CFile [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) с помощью побитового или (|) оператор. Разрешение на доступ один параметр одной общей папки требуются и; **modeCreate** и **modeNoInherit** режимы являются необязательными.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `CFile`.  
  
##  <a name="a-namegetfirstviewpositiona--cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>CDocument::GetFirstViewPosition  
 Эта функция вызывается для получения позиции первое представление в списке представления, связанные с данным документом.  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации с помощью [GetNextView](#getnextview) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetnextviewa--cdocumentgetnextview"></a><a name="getnextview"></a>CDocument::GetNextView  
 Эта функция вызывается для перебора всех представлений документа.  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rPosition`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим вызовом `GetNextView` или [GetFirstViewPosition](#getfirstviewposition) функции-члены. Это значение не должно быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на представление, идентифицируемый `rPosition`.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает представление, идентифицируемый `rPosition` , а затем присваивает `rPosition` для **ПОЗИЦИИ** значение следующего представления в списке. Если полученный представление является последним в списке, затем `rPosition` равен **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetpathnamea--cdocumentgetpathname"></a><a name="getpathname"></a>CDocument::GetPathName  
 Эта функция вызывается для получения полный путь файла документа.  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный путь к документу. Эта строка пуста, если документ не был сохранен или не имеет связанного с ним файла на диске.  
  
##  <a name="a-namegetthumbnaila--cdocumentgetthumbnail"></a><a name="getthumbnail"></a>CDocument::GetThumbnail  
 Создает растровое изображение для использования поставщика уменьшенных изображений для отображения эскиза.  
  
```  
virtual BOOL GetThumbnail(
    UINT cx,  
    HBITMAP* phbmp,  
    DWORD* pdwAlpha);
```  
  
### <a name="parameters"></a>Параметры  
 `cx`  
 Задает ширину и высоту изображения.  
  
 `phbmp`  
 Содержит дескриптор точечного рисунка, когда функция возвращает успешно.  
  
 `pdwAlpha`  
 Содержит значение DWORD, указав значение альфа-канала при успешном возврате функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если растровое изображение для эскиза была создана успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegettitlea--cdocumentgettitle"></a><a name="gettitle"></a>CDocument::GetTitle  
 Эта функция вызывается для получения название документа, который обычно является производным от имени файла документа.  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Название документа.  
  
##  <a name="a-nameinitializesearchcontenta--cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>CDocument::InitializeSearchContent  
 Вызывается для инициализации поиск содержимого для поиска обработчика.  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод в производном классе для инициализации поиск содержимого. Содержимое должно быть строкой с частей, разделенных «;». Например «точки; прямоугольник; элемент OLE».  
  
##  <a name="a-nameismodifieda--cdocumentismodified"></a><a name="ismodified"></a>CDocument::IsModified  
 Эта функция вызывается для определения ли документ был изменен с момента последнего сохранения.  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ был изменен с момента последнего сохранения; в противном случае — 0.  
  
##  <a name="a-nameissearchandorganizehandlera--cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>CDocument::IsSearchAndOrganizeHandler  
 Сообщает ли этот экземпляр `CDocument` был создан для обработчика упорядочить & поиска.  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если этот экземпляр `CDocument` был создан для обработчика упорядочить & поиска.  
  
### <a name="remarks"></a>Примечания  
 В настоящее время эта функция возвращает `TRUE` только для расширенного просмотра обработчиков, реализованы в развертывании сервера обработки. Можно задать соответствующие флаги (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) на уровень приложения, чтобы эта функция возвращаемого `TRUE`.  
  
##  <a name="a-nameloaddocumentfromstreama--cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>CDocument::LoadDocumentFromStream  
 Вызывается, чтобы загрузить данные документа из потока.  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 Указатель на поток. Этот поток предоставлен оболочки.  
  
 `dwGrfMode`  
 Режим доступа к потоку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция загрузки выполнена успешно, в противном случае — значение HRESULT с кодом ошибки.  
  
### <a name="remarks"></a>Примечания  
 Можно переопределить этот метод в производном классе, чтобы настроить способ загрузки данных из потока.  
  
##  <a name="a-namembgetthumbnailmodea--cdocumentmbgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>CDocument::m_bGetThumbnailMode  
 Указывает, что `CDocument` объект был создан с dllhost для эскизов. Следует проверить `CView::OnDraw`.  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>Примечания  
 `TRUE`Указывает, что документ был создан с dllhost для эскизов.  
  
##  <a name="a-namembpreviewhandlermodea--cdocumentmbpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>CDocument::m_bPreviewHandlerMode  
 Указывает, что `CDocument` был создан объект с prevhost для расширенного просмотра. Следует проверить `CView::OnDraw`.  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>Примечания  
 `TRUE`Указывает, что документ был создан с prevhost для расширенного просмотра.  
  
##  <a name="a-namembsearchmodea--cdocumentmbsearchmode"></a><a name="m_bsearchmode"></a>CDocument::m_bSearchMode  
 Указывает, что `CDocument` был создан объект индексатором или другим приложением поиска.  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>Примечания  
 `TRUE`Указывает, что был создан документ индексатором или другим приложением поиска.  
  
##  <a name="a-namemclrrichpreviewbackcolora--cdocumentmclrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>CDocument::m_clrRichPreviewBackColor  
 Задает цвет фона окна расширенного просмотра. Этот цвет задан узлом.  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namemclrrichpreviewtextcolora--cdocumentmclrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>CDocument::m_clrRichPreviewTextColor  
 Задает цвет переднего плана в окне расширенного просмотра. Этот цвет задан узлом.  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namemlfrichpreviewfonta--cdocumentmlfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>CDocument::m_lfRichPreviewFont  
 Задает шрифт текста в окне расширенного просмотра. Эта информация шрифт задается узлом.  
  
```  
CFont m_lfRichPreviewFont;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonbeforerichpreviewfontchangeda--cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>CDocument::OnBeforeRichPreviewFontChanged  
 Вызывается перед изменением шрифта расширенного просмотра.  
  
```  
virtual void OnBeforeRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonchangedviewlista--cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>CDocument::OnChangedViewList  
 Вызывается платформой после представления добавлен или удален из документа.  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция проверяет последнее представление удаляется и, если это так, удаляет документ. Переопределите эту функцию, если вы хотите выполнять специальную обработку, когда платформа добавляет или удаляет представления. Например документ оставаться открытым, даже в том случае, если нет представлений, присоединенные к ней следует переопределите эту функцию.  
  
##  <a name="a-nameonclosedocumenta--cdocumentonclosedocument"></a><a name="onclosedocument"></a>CDocument::OnCloseDocument  
 Вызывается платформой после закрытия документа, обычно как часть команды File Close.  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция удаляет все кадры, используется для просмотра документа, закрывает представление, очищает содержимое документа и затем вызывает метод [DeleteContents](#deletecontents) функция-член для удаления данных документа.  
  
 Переопределите эту функцию, если требуется выполнять обработку специальные операции очистки, когда платформа framework закрывает документ. Например документ представляет запись в базе данных, можно переопределить эту функцию для закрытия базы данных. Версия этой функции базового класса следует вызывать из переопределения.  
  
##  <a name="a-nameoncreatepreviewframea--cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>CDocument::OnCreatePreviewFrame  
 Вызывается платформой, когда он должен создать рамки предварительной версии для расширенного просмотра.  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если создания рамки успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameondocumenteventa--cdocumentondocumentevent"></a><a name="ondocumentevent"></a>CDocument::OnDocumentEvent  
 Вызывается средой в ответ на событие документа.  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `deEvent`  
 Тип перечислимых данных, который описывает тип события.  
  
### <a name="remarks"></a>Примечания  
 События документа может повлиять на несколько классов. Этот метод отвечает за обработку события документа, не влияющие на классы [CDocument-класс](../../mfc/reference/cdocument-class.md). В настоящее время является единственным классом, должен отвечать на события документа [CDataRecoveryHandler класса](../../mfc/reference/cdatarecoveryhandler-class.md). `CDocument` Класс имеет другие переопределяемые методы отвечает за обработку эффект `CDocument`.  
  
 В следующей таблице перечислены возможные значения для `deEvent` и события, которые они соответствуют.  
  
|Значение|Соответствующее событие|  
|-----------|-------------------------|  
|`onAfterNewDocument`|Был создан новый документ.|  
|`onAfterOpenDocument`|Новый документ был открыт.|  
|`onAfterSaveDocument`|Документ был сохранен.|  
|`onAfterCloseDocument`|Документ был закрыт.|  
  
##  <a name="a-nameondrawthumbnaila--cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>CDocument::OnDrawThumbnail  
 Переопределите этот метод в производном классе для рисования эскиз.  
  
```  
virtual void OnDrawThumbnail(
    CDC& dc,  
    LPRECT lprcBounds);
```  
  
### <a name="parameters"></a>Параметры  
 `dc`  
 Ссылка на контекст устройства.  
  
 `lprcBounds`  
 Указывает ограничивающий прямоугольник области, где должен отображаться эскиз.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonfilesendmaila--cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>CDocument::OnFileSendMail  
 Отправляет сообщение через узел резидентного почтового (если таковые имеются) в документе как вложение.  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>Примечания  
 `OnFileSendMail`вызовы [OnSaveDocument](#onsavedocument) для сериализации (безымянный и измененных документов во временный файл, который затем отправляется по электронной почте Сохранить). Если документ не был изменен, временный файл не требуется; Исходное отправленное. `OnFileSendMail`Загружает MAPI32. Библиотека DLL, если он еще не загружена.  
  
 Специальные реализации `OnFileSendMail` для [COleDocument](../../mfc/reference/coledocument-class.md) дескрипторы составные файлы правильно.  
  
 **CDocument** поддерживает отправку документа электронной почте при наличии поддержки электронной почты (MAPI). См. в статьях [разделы MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="a-nameonloaddocumentfromstreama--cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>CDocument::OnLoadDocumentFromStream  
 Вызывается платформой, когда это необходимо загрузить данные документа из потока.  
  
```  
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,  
    DWORD grfMode);
```  
  
### <a name="parameters"></a>Параметры  
 `pStream`  
 Указатель на входной поток.  
  
 `grfMode`  
 Режим доступа к потоку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если загрузка прошла успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonnewdocumenta--cdocumentonnewdocument"></a><a name="onnewdocument"></a>CDocument::OnNewDocument  
 Вызывается платформой как часть команды File New.  
  
```  
virtual BOOL OnNewDocument();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ был успешно инициализирован; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция вызывает [DeleteContents](#deletecontents) убедитесь, что документ является пустым и затем помечает новый документ как чистая функция-член. Переопределите эту функцию, чтобы инициализировать структуру данных для нового документа. Версия этой функции базового класса следует вызывать из переопределения.  
  
 При выборе команды Создать файл в приложении SDI, платформа использует эту функцию для повторной инициализации существующих документов, а не создавать новую. Если пользователь выбирает новый файл в приложении несколько интерфейса (MDI) документа, платформа создает новый документ и затем вызывает эту функцию для его инициализации. В этой функции, а не в конструктор для файла новой команды для эффективного SDI-приложения, необходимо поместить код инициализации.  
  
 Обратите внимание, что существуют ситуации, когда `OnNewDocument` вызывается дважды. Это происходит, когда документ внедрен как сервер документов ActiveX. Сначала вызывается функция `CreateInstance` метод (предоставляемый `COleObjectFactory`-производного класса) и второй раз с `InitNew` метод (предоставляемый `COleServerDoc`-производного класса).  
  
### <a name="example"></a>Пример  
 Следующие примеры иллюстрируют альтернативные методы инициализации объекта документа.  
  
 [!code-cpp[NVC_MFCDocView&#60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="a-nameonopendocumenta--cdocumentonopendocument"></a><a name="onopendocument"></a>CDocument::OnOpenDocument  
 Вызывается платформой как часть команды открытия файла.  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPathName`  
 Указывает путь для открываемого документа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ был успешно загружен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция открывает указанный файл, вызовы [DeleteContents](#deletecontents) убедитесь, что документ является пустым, функция-член вызывает [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для чтения файла, содержимое, а затем помечает документ как очистить. Переопределите эту функцию, если вы хотите использовать что-либо отличное от механизма архива или механизм файла. Например можно написать приложение, где документы представляют записи в базу данных, а не отдельные файлы.  
  
 При выборе команды Открыть файл в приложении SDI, платформа использует эту функцию для повторной инициализации существующих **CDocument** объекта, а не создавать новую. Если пользователь выберет открытие файла в приложение MDI, платформа создает новое **CDocument** объект каждый раз, а затем вызывает эту функцию для его инициализации. В этой функции, а не в конструкторе для команды открытия файла для эффективного SDI-приложения, необходимо поместить код инициализации.  
  
### <a name="example"></a>Пример  
 Следующие примеры иллюстрируют альтернативные методы инициализации объекта документа.  
  
 [!code-cpp[NVC_MFCDocView&#60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#63;](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="a-nameonpreviewhandlerqueryfocusa--cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>CDocument::OnPreviewHandlerQueryFocus  
 Указывает обработчик просмотра для возврата HWND извлекаются из вызова метода `GetFocus` функции.  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>Параметры  
 `phwnd`  
 [out] При возвращении данного метода содержит указатель на HWND, возвращаемый вызовом `GetFocus` функции из обработчика просмотра основного потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK, если выполнено успешно; или, в противном случае — значение ошибки.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonpreviewhandlertranslateacceleratora--cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>CDocument::OnPreviewHandlerTranslateAccelerator  
 Указывает обработчик просмотра для обработки нажатия клавиш, передаются из средства переноса сообщений процесса, в котором выполняется обработчик просмотра.  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pmsg`  
 [in] Указатель на окно сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если нажатие клавиши сообщения могут обрабатываться обработчика просмотра, обработчик обрабатывает его и возвращает значение S_OK. Если обработчик просмотра не удается обработать сообщение нажатия клавиш, он предлагает его узла с помощью `IPreviewHandlerFrame::TranslateAccelerator`. Если узел обрабатывает сообщение, этот метод возвращает значение S_OK. Если узел не обрабатывает сообщения, этот метод возвращает значение S_FALSE.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonrichpreviewbackcolorchangeda--cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>CDocument::OnRichPreviewBackColorChanged  
 Вызывается при изменении цвета фона расширенного просмотра.  
  
```  
virtual void OnRichPreviewBackColorChanged();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonrichpreviewfontchangeda--cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>CDocument::OnRichPreviewFontChanged  
 Вызывается при изменении шрифта расширенного просмотра.  
  
```  
virtual void OnRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonrichpreviewsitechangeda--cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>CDocument::OnRichPreviewSiteChanged  
 Вызывается при изменении расширенного просмотра сайта.  
  
```  
virtual void OnRichPreviewSiteChanged();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonrichpreviewtextcolorchangeda--cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>CDocument::OnRichPreviewTextColorChanged  
 Вызывается при изменении цвета текста расширенного просмотра.  
  
```  
virtual void OnRichPreviewTextColorChanged();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonsavedocumenta--cdocumentonsavedocument"></a><a name="onsavedocument"></a>CDocument::OnSaveDocument  
 Вызывается платформой как часть команды сохранения файла или сохранение файла.  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPathName`  
 Указывает полный путь для сохранения файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если документ был успешно сохранен; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция открывает указанный файл, вызовы [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для записи данных документа в файл, а затем метки документ как очистить. Переопределите эту функцию, если вы хотите выполнять специальную обработку, когда платформа сохраняет документ. Например можно написать приложение, где документы представляют записи в базу данных, а не отдельные файлы.  
  
##  <a name="a-nameonunloadhandlera--cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>CDocument::OnUnloadHandler  
 Вызывается инфраструктурой при выгрузке обработчика просмотра.  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameonupdatefilesendmaila--cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>CDocument::OnUpdateFileSendMail  
 Позволяет **ID_FILE_SEND_MAIL** команду, если имеется поддержка почты (MAPI).  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Параметры  
 `pCmdUI`  
 Указатель на [CCmdUI](../../mfc/reference/ccmdui-class.md) объекта, связанного с **ID_FILE_SEND_MAIL** команды.  
  
### <a name="remarks"></a>Примечания  
 В противном случае функция удаляет **ID_FILE_SEND_MAIL** команды меню, включая разделители выше или ниже меню элемента в зависимости от необходимости. При включении MAPI MAPI32. DLL присутствует в пути и в разделе [почты] WIN. INI-файл, MAPI =&1;. Большинство приложений поместить эту команду в меню файл.  
  
 **CDocument** поддерживает отправку документа электронной почте при наличии поддержки электронной почты (MAPI). См. в статьях [разделы MAPI](../../mfc/mapi.md) и [поддержка MAPI в MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="a-nameprecloseframea--cdocumentprecloseframe"></a><a name="precloseframe"></a>CDocument::PreCloseFrame  
 Эта функция-член вызывается платформой, перед удалением фрейме окна.  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Параметры  
 `pFrame`  
 Указатель на [CFrameWnd](../../mfc/reference/cframewnd-class.md) , содержащий связанный **CDocument** объекта.  
  
### <a name="remarks"></a>Примечания  
 Он может быть переопределен для предоставления пользовательских очистки, но не забудьте вызвать базовый класс также.  
  
 Значение по умолчанию для `PreCloseFrame` не выполняет никаких действий **CDocument**. **CDocument**-производные классы [COleDocument](../../mfc/reference/coledocument-class.md) и [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) использовать эту функцию-член.  
  
##  <a name="a-namereadnextchunkvaluea--cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>CDocument::ReadNextChunkValue  
 Считывает значение следующего фрагмента.  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>Параметры  
 `ppValue`  
 [out] При возврате из функции `ppValue` содержит значение, которое было прочитано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namereleasefilea--cdocumentreleasefile"></a><a name="releasefile"></a>CDocument::ReleaseFile  
 Эта функция-член вызывается платформой для выпуска файла, делая доступными для использования другими приложениями.  
  
```  
virtual void ReleaseFile(
    CFile* pFile,  
    BOOL bAbort);
```  
  
### <a name="parameters"></a>Параметры  
 `pFile`  
 Указатель на объект CFile, освобождается.  
  
 `bAbort`  
 Указывает, является ли файл должна освобождаться с помощью `CFile::Close` или `CFile::Abort`. **FALSE** Если файл должен освобождаться с помощью [CFile::Close](../../mfc/reference/cfile-class.md#close); **TRUE** Если файл должен освобождаться с помощью [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="remarks"></a>Примечания  
 Если `bAbort` — **TRUE**, `ReleaseFile` вызовы `CFile::Abort`, и файл освобождается. `CFile::Abort`не будет выдано исключение.  
  
 Если `bAbort` — **FALSE**, `ReleaseFile` вызовы `CFile::Close` и освободить файл.  
  
 Переопределите эту функцию-член требуется действие пользователя до освобождения файла.  
  
##  <a name="a-nameremovechunka--cdocumentremovechunk"></a><a name="removechunk"></a>CDocument::RemoveChunk  
 Удаляет фрагмент данных с указанным идентификатором GUID.  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Параметры  
 `Guid`  
 Задает идентификатор GUID блока, должны быть удалены.  
  
 `Pid`  
 Указывает PID блока, должны быть удалены.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameremoveviewa--cdocumentremoveview"></a><a name="removeview"></a>CDocument::RemoveView  
 Эта функция вызывается для отсоединения представления из документа.  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>Параметры  
 `pView`  
 Указывает удаляемый представления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция удаляет указанное представление из списка представлений, связанные с данным документом; Он также устанавливает указатель представление документа в **NULL**. Эта функция вызывается инфраструктурой при закрытии окна фрейма или область окна-разделителя закрыта.  
  
 Эта функция вызывается только в том случае, если вручную отсоединение представления. Обычно позволит платформа отсоединить документов и представлений, определив [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) для привязки класса документов, представления класса и класс фреймового окна.  
  
 Можно найти в [добавить представление](#addview) пример реализации.  
  
##  <a name="a-namereportsaveloadexceptiona--cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>CDocument::ReportSaveLoadException  
 Вызывается, если исключение (обычно [CFileException](../../mfc/reference/cfileexception-class.md) или [CArchiveException](../../mfc/reference/carchiveexception-class.md)) во время сохранения или загрузки документа.  
  
```  
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,  
    CException* e,  
    BOOL bSaving,  
    UINT nIDPDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPathName`  
 Указывает имя документа, которая находится в процессе сохранения или загрузки.  
  
 *e*  
 Указывает исключение, которое было создано. Может быть **NULL**.  
  
 *bSaving*  
 Флаг, указывающий, какая операция выполнялась; ненулевое значение, если документ был были сохранены, 0 Если загружен документ.  
  
 `nIDPDefault`  
 Идентификатор сообщения об ошибке, отображаемое, если функция не содержит более определенными.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию проверяет объекта исключения и ищет сообщения об ошибке, в частности описывает причину. Если сообщение не найден или *e* — **NULL**, общие сообщения, заданного `nIDPDefault` используется параметр. Функция затем отображает окно сообщения, содержащее сообщение об ошибке. Переопределите эту функцию, если требуется предоставить дополнительные, настраиваемых сообщений. Существует расширенная переопределяемыми.  
  
##  <a name="a-namesavemodifieda--cdocumentsavemodified"></a><a name="savemodified"></a>CDocument::SaveModified  
 Вызывается платформой до измененный документ будет закрыт.  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если безопасно продолжить и закрыть документ; 0, если документ не был закрыт.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция отображает окно сообщения, запрашивающее пользователя, следует ли сохранить изменения в документе, если они были внесены. Переопределите эту функцию, если приложение требует другую процедуру запроса. Существует расширенная переопределяемыми.  
  
##  <a name="a-namesetchunkvaluea--cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>CDocument::SetChunkValue  
 Задает значение фрагмента данных.  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Параметры  
 `pValue`  
 Указывает значение фрагмента данных.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namesetmodifiedflaga--cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>CDocument::SetModifiedFlag  
 Эта функция вызывается после внесения изменений в документ.  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bModified`  
 Флаг, указывающее, был ли изменен документ.  
  
### <a name="remarks"></a>Примечания  
 Вызов этой функции постоянно, убедитесь, что платформа предлагает пользователю сохранить изменения перед закрытием документа. Обычно следует использовать значение по умолчанию **TRUE** для `bModified` параметр. Чтобы пометить документ как очистить (без изменений), эта функция со значением **FALSE**.  
  
##  <a name="a-namesetpathnamea--cdocumentsetpathname"></a><a name="setpathname"></a>CDocument::SetPathName  
 Эта функция вызывается для укажите полный путь файла документа.  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPathName`  
 Указывает строку для использования в качестве пути для документа.  
  
 `bAddToMRU`  
 Определяет, используется ли имя файла добавляется в наиболее недавно списка файлов (MRU). Если **значение TRUE,** добавляется имя файла; если **FALSE**, он не добавляется.  
  
### <a name="remarks"></a>Примечания  
 В зависимости от значения `bAddToMRU` добавляется путь, или не добавляется в список последних Использованных поддерживается приложением. Обратите внимание, что некоторые документы не связаны с файлом диска. Эта функция вызывается только в том случае, если выполняется переопределение реализация по умолчанию для открытия и сохранения файлов, используемых платформой.  
  
##  <a name="a-namesettitlea--cdocumentsettitle"></a><a name="settitle"></a>CDocument::SetTitle  
 Эта функция вызывается для указания название документа (строку, отображаемую в строке заголовка окна фрейма).  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszTitle`  
 Указывает строку, используемый как название документа.  
  
### <a name="remarks"></a>Примечания  
 При вызове этой функции обновляет заголовки всех окон фрейма, отобразить документ.  
  
##  <a name="a-nameupdateallviewsa--cdocumentupdateallviews"></a><a name="updateallviews"></a>CDocument::UpdateAllViews  
 Эта функция вызывается после изменения документа.  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pSender`  
 Указывает представление, изменение в документ или **NULL** Если все представления должны быть обновлены.  
  
 `lHint`  
 Содержит сведения об изменении.  
  
 `pHint`  
 Указывает для хранения сведений об изменении объекта.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию следует вызывать после вызова [SetModifiedFlag](#setmodifiedflag) функции-члена. Эта функция сообщает каждого представления, прикрепленной к документу, за исключением представление, указанное в `pSender`, что документ был изменен. Вызов этой функции из представления класса после документа через представление было изменено пользователем.  
  
 Эта функция вызывает функцию [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) просмотреть функции-члена для каждого представления документа, за исключением отправку, передав `pHint` и `lHint`. Эти параметры можно используйте для передачи информации представления об изменениях, внесенных в документ. Можно закодировать с помощью сведения `lHint` или можно определить [CObject](../../mfc/reference/cobject-class.md)-производный класс для хранения информации об изменениях и передайте объект этого класса, используя `pHint`. Переопределение `CView::OnUpdate` функции-члена в вашей [CView](../../mfc/reference/cview-class.md)-производный класс для оптимизации обновление отображения представления на основе данных передается.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#64;](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>См. также  
 [MFC примера MDIDOCVW](../../visual-cpp-samples.md)   
 [Пример MFC SNAPVW](../../visual-cpp-samples.md)   
 [Пример MFC NPP](../../visual-cpp-samples.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [CDocTemplate-класс](../../mfc/reference/cdoctemplate-class.md)

