---
title: CDocTemplate-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7674e9a25f4794d40a977fce914ab6ac0131de25
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdoctemplate-class"></a>CDocTemplate-класс
Абстрактный базовый класс, который определяет базовую функциональность шаблонов документов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocTemplate::CDocTemplate](#cdoctemplate)|Создает объект `CDocTemplate`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDocTemplate::AddDocument](#adddocument)|Добавляет документ в шаблон.|  
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|Закрывает все документы, связанные с этим шаблоном.|  
|[CDocTemplate::CreateNewDocument](#createnewdocument)|Создает новый документ.|  
|[CDocTemplate::CreateNewFrame](#createnewframe)|Создает новое окно фрейма, содержащего документа и представления.|  
|[CDocTemplate::CreateOleFrame](#createoleframe)|Создает окно фрейма поддержкой OLE.|  
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Создает дочерний кадр, используемый для расширенного просмотра.|  
|[CDocTemplate::GetDocString](#getdocstring)|Возвращает строку, связанную с типом документа.|  
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Возвращает позицию первого документа, связанный с этим шаблоном.|  
|[CDocTemplate::GetNextDoc](#getnextdoc)|Получает документ и положение следующего.|  
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Инициализирует фрейм окна, а также делает ее видимой.|  
|[CDocTemplate::LoadTemplate](#loadtemplate)|Загружает ресурсы для данного `CDocTemplate` или производного класса.|  
|[CDocTemplate::MatchDocType](#matchdoctype)|Определяет степень уверенности в соответствие между типом документа и этот шаблон.|  
|[Функции](#opendocumentfile)|Открывает файл, указанный параметром pathname.|  
|[CDocTemplate::RemoveDocument](#removedocument)|Удаляет документ из шаблона.|  
|[CDocTemplate::SaveAllModified](#saveallmodified)|Сохранение всех документов, связанный с этим шаблоном, которые были изменены.|  
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|Определяет ресурсы для OLE-контейнеры, при редактировании объекта OLE на месте.|  
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|Отображает заголовок по умолчанию в строке заголовка окна документа.|  
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|Настройки вне процесса предварительного просмотра обработчик.|  
|[CDocTemplate::SetServerInfo](#setserverinfo)|Определяет ресурсы и классы, когда серверный документ внедряется или редактируется по месту.|  
  
## <a name="remarks"></a>Примечания  
 Реализация приложения обычно создается один или несколько шаблонов документов `InitInstance` функции. Шаблон документа определяет отношения между три типа классов:  
  
-   Класс документа, который можно создать производный от **CDocument**.  
  
-   Класс представления отображаются данные из класса документа, перечисленных выше. Можно наследовать от этого класса `CView`, `CScrollView`, `CFormView`, или `CEditView`. (Можно также использовать `CEditView` напрямую.)  
  
-   Класс окна фрейма, который содержит представление. Однооконный интерфейс (SDI) приложения, необходимо наследовать от этого класса `CFrameWnd`. Для нескольких приложений интерфейса (MDI) документа, необходимо наследовать от этого класса `CMDIChildWnd`. Если не нужно настраивать поведение фрейм окна, можно использовать `CFrameWnd` или `CMDIChildWnd` напрямую без создания собственного производного класса.  
  
 Ваше приложение имеет один шаблон документа для каждого типа документа, который он поддерживает. Например если приложение поддерживает электронные таблицы и текстовые документы, приложение имеет два объекта шаблона документа. Каждый шаблон документа отвечает за создание и управление ими все документы его типа.  
  
 Шаблон документа хранит указатели на `CRuntimeClass` объектов для документов, представления и классы окна фрейма. Эти `CRuntimeClass` объекты указываются при создании шаблона документа.  
  
 Шаблон документа содержит идентификатор ресурсы, используемые с типом документа (например, меню, значка или ресурсами таблиц сочетаний клавиш). Шаблон документа также содержит строки, содержащие дополнительные сведения о его тип документа. К ним относятся имя типа документа (например, «лист») и расширение файла (например, «.xls»). При необходимости оно может содержать другие строки, используемые интерфейс пользователя, диспетчер файлов и связывание объекта и поддержка внедрения (OLE).  
  
 Если приложение является OLE-контейнер и/или сервер, шаблон документа также определяет идентификатор меню, используемое во время активации на месте. Если приложение является OLE-сервер, шаблон документа определяет идентификатор панели инструментов и меню, которое используется во время активации на месте. Укажите следующие дополнительные ресурсы OLE путем вызова `SetContainerInfo` и `SetServerInfo`.  
  
 Поскольку `CDocTemplate` — это абстрактный класс, класс нельзя использовать напрямую. Типичное приложение использует один из двух `CDocTemplate`-производные классы, предоставляемые библиотекой классов Microsoft Foundation: `CSingleDocTemplate`, который реализует SDI, и `CMultiDocTemplate`, который реализует MDI. Эти классы для получения дополнительной информации см. по использованию шаблонов документов.  
  
 Если приложение требует парадигма пользовательского интерфейса, который существенно отличается от SDI или MDI, можно создать собственный класс, от `CDocTemplate`.  
  
 Дополнительные сведения о `CDocTemplate`, в разделе [шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="adddocument"></a>  CDocTemplate::AddDocument  
 Эта функция используется для добавления в шаблон документа.  
  
```  
virtual void AddDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Указатель на документ, который нужно добавить.  
  
### <a name="remarks"></a>Примечания  
 Производные классы [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) и [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) переопределить эту функцию. При наследовании класса шаблона документа из `CDocTemplate`, эту функцию необходимо переопределить производный класс.  
  
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
 `nIDResource`  
 Указывает идентификатор ресурсы, используемые с типом документа. Это может включать меню, значок, таблицу сочетаний клавиш и строковые ресурсы.  
  
 Строковый ресурс состоит из до семи подстроки, разделенных знаком «\n» (символ «\n», необходимое в качестве заполнителя Если подстрока не указан; конечные символы «\n» не нужны); Эти подстроки описания типа документа. Сведения о подстроках см. в разделе [GetDocString](#getdocstring). Этот строковый ресурс находится в файле ресурсов приложения. Пример:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Обратите внимание, что строка начинается с символа '\n'; Это происходит потому, первая подстрока не используется в приложениях MDI и не включается. Можно изменить эту строку, с помощью редактора; вся строка отображается как единственная запись в редакторе строку не как семь отдельные записи.  
  
 `pDocClass`  
 Указывает `CRuntimeClass` объекта класса документа. Этот класс является **CDocument**-производный класс, определенный для представления документов.  
  
 `pFrameClass`  
 Указывает на `CRuntimeClass` объект класс окна фрейма. Этот класс может быть `CFrameWnd`-производного класса, или он может быть `CFrameWnd` себя, если требуется поведение по умолчанию для главного окна фрейма.  
  
 `pViewClass`  
 Указывает `CRuntimeClass` объекта класса представления. Этот класс является `CView`-производный класс, определяемый для отображения документов.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член для создания `CDocTemplate` объекта. Динамически выделять `CDocTemplate` и передать его на [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) из `InitInstance` функцию-член класса приложения.  
  
##  <a name="closealldocuments"></a>  CDocTemplate::CloseAllDocuments  
 Вызовите эту функцию-член, чтобы закрыть все открытые документы.  
  
```  
virtual void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Параметры  
 `bEndSession`  
 Указывает, выполняется ли сеанс заканчивается. Это **TRUE** Если сеанс завершается; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член обычно используется в команде выхода в файл. Реализация по умолчанию эта функция вызывает [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) функция-член для удаления документа данных, а затем закрытия окна фрейма для всех представлений, прикрепленного к документу.  
  
 Переопределите эту функцию, чтобы требовать от пользователя выполнять обработку специальные операции очистки, перед закрытием документа. Например документ представляет собой запись в базе данных, можно переопределить эту функцию, чтобы закрыть базу данных.  
  
##  <a name="createnewdocument"></a>  CDocTemplate::CreateNewDocument  
 Вызовите эту функцию-член для создания нового документа, тип которого связан с шаблоном документа.  
  
```  
virtual CDocument* CreateNewDocument();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданного документа или **NULL** при возникновении ошибки.  
  
##  <a name="createnewframe"></a>  CDocTemplate::CreateNewFrame  
 Создает новое окно фрейма, содержащего документа и представления.  
  
```  
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,  
    CFrameWnd* pOther);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Документ, на который должна ссылаться нового окна области. Может быть **NULL**.  
  
 `pOther`  
 Окна фрейма, на которой будет основываться нового окна области. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный фрейме окна, или **NULL** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 `CreateNewFrame` использует `CRuntimeClass` объекты передаются в конструктор, чтобы создать новый объект окна представление и вложенный документ. Если `pDoc` параметр **NULL**, платформа выводит сообщение ТРАССИРОВКИ.  
  
 `pOther` Параметр используется для реализации команду создания окна. Он предоставляет окно фрейма, в котором для моделирования нового окна области. Обычно создается невидимой нового окна области. Эта функция вызывается для создания окна фрейма за пределами реализации стандартной платформы для новых файлов и открытие файла.  
  
##  <a name="createoleframe"></a>  CDocTemplate::CreateOleFrame  
 Создает окно фрейма OLE.  
  
```  
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc,  
    BOOL bCreateView);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительское окно фрейма.  
  
 `pDoc`  
 Указатель на документ, на который должна ссылаться новое окно фрейма OLE.  
  
 `bCreateView`  
 Определяет, создается ли представление вместе с фрейма.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно фрейма, в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `bCreateView` равен нулю, создается пустая рамка.  
  
##  <a name="getdocstring"></a>  CDocTemplate::GetDocString  
 Возвращает строку, связанную с типом документа.  
  
```  
virtual BOOL GetDocString(
    CString& rString,  
    enum DocStringIndex index) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rString`  
 Ссылку на `CString` объект, который будет содержать строку, когда функция возвращает.  
  
 *Индекс*  
 Индекс подстроки, извлекаемых из строку, которая описывает тип документа. Этот параметр может принимать одно из следующих значений:  
  
- **CDocTemplate::windowTitle** имя, которое отображается в строке (например, «Microsoft Excel») заголовка окна приложения. Представление только в шаблоне документа для SDI-приложения.  
  
- **CDocTemplate::docName** корневого имени по умолчанию документ (например, «Таблицы»). Этого корня, вместе с номером используется имя по умолчанию новый документ этого типа всякий раз, когда пользователь выбирает новой команды из меню «файл» (например, «Лист1» или «Лист2»). Если не указан, «Без имени» используется как значение по умолчанию.  
  
- **CDocTemplate::fileNewName** имя этого типа документа. Если приложение поддерживает более чем один тип документа, эта строка отображается в диалоговом окне новый файл (например, «лист»). Если не указан, тип документа недоступна с помощью команды создания файла.  
  
- **CDocTemplate::filterName** описание типа документа, а также соответствующие документы этого типа фильтра с подстановочными знаками. Эта строка отображается в раскрывающемся списке Тип файлов в диалоговом окне открытия файла (например, «рабочие листы Excel (*.xls)»). Если не указан, тип документа недоступна с помощью команды открытия файла.  
  
- **CDocTemplate::filterExt** расширение для документов этого типа (например, «.xls»). Если не указан, тип документа недоступна с помощью команды открытия файла.  
  
- **CDocTemplate::regFileTypeId** идентификатор типа документа должен храниться в регистрационную базу данных поддерживаются операционной системой Windows. Эта строка представляет только для внутреннего использования (например, «ExcelWorksheet»). Если не указан, тип документа не удается зарегистрировать с помощью диспетчера файлов Windows.  
  
- **CDocTemplate::regFileTypeName** имя типа документа должен храниться в базе данных регистрации. Эта строка может отображаться в диалоговых окнах приложений, получающих доступ к базе данных регистрации (например, «лист Microsoft Excel»).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если указанная подстрока был найден. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения конкретной подстроки, описывающий тип документа. Строка, содержащая эти подстроки хранится в шаблон документа, а также является производным от строки в файле ресурсов для приложения. Платформа вызывает эту функцию для получения строк, которые необходимы для пользовательского интерфейса приложения. При указании расширения имени файла для документов приложения платформа также вызывает эту функцию при добавлении записи в базу данных Windows для регистрации. Это позволяет документы будут открываться в диспетчере файлов Windows.  
  
 Эта функция вызывается только при наследовании класса из `CDocTemplate`.  
  
##  <a name="getfirstdocposition"></a>  CDocTemplate::GetFirstDocPosition  
 Возвращает позицию первого документа, связанный с этим шаблоном.  
  
```  
virtual POSITION GetFirstDocPosition() const = 0;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации по списку документов, связанных с шаблоном документа; или **NULL** Если список пуст.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для получения позиции первого документа в список документов, связанных с этим шаблоном. Используйте **ПОЗИЦИИ** значение в качестве аргумента для [CDocTemplate::GetNextDoc](#getnextdoc) для итерации по списку документов, связанных с шаблоном.  
  
 [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) и [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) переопределяется это чистой виртуальной функции. Любой класс, производный от `CDocTemplate` необходимо также переопределить эту функцию.  
  
##  <a name="getnextdoc"></a>  CDocTemplate::GetNextDoc  
 Извлекает список элемент, идентифицируемый `rPos`, затем устанавливает `rPos` для **ПОЗИЦИИ** значение на следующую запись в списке.  
  
```  
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на следующий документ в список документов, связанных с этим шаблоном.  
  
### <a name="parameters"></a>Параметры  
 `rPos`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим вызовом [GetFirstDocPosition](#getfirstdocposition) или `GetNextDoc`.  
  
### <a name="remarks"></a>Примечания  
 Если полученный элемент является последним в списке, то новое значение `rPos` равно **NULL**.  
  
 Можно использовать `GetNextDoc` в прямой итерации цикла, если установить начальное положение, с помощью вызова [GetFirstDocPosition](#getfirstdocposition).  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, подтверждает отладочной версии библиотеки классов Microsoft Foundation.  
  
##  <a name="initialupdateframe"></a>  CDocTemplate::InitialUpdateFrame  
 Инициализирует фрейм окна, а также делает ее видимой.  
  
```  
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,  
    CDocument* pDoc,  
    BOOL bMakeVisible = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pFrame`  
 Окна фрейма, которому требуется начальное обновление.  
  
 `pDoc`  
 Документ, с которым связано фрейма. Может быть **NULL**.  
  
 `bMakeVisible`  
 Указывает ли кадр должен быть видимым и активной.  
  
### <a name="remarks"></a>Примечания  
 Вызовите **IntitialUpdateFrame** после создания новой рамки с `CreateNewFrame`. Вызов этой функции приводит представления в это окно фрейма для получения их `OnInitialUpdate` вызовов. Кроме того Если не было ранее активное представление, первичное представление окна фрейма делается активным; основное представление — это представление с ИД дочернего объекта **AFX_IDW_PANE_FIRST**. Наконец, окно фрейма становится видимым при `bMakeVisible` не равно нулю. Если `bMakeVisible` равен нулю, текущего местоположения и видимое состояние окна фрейма останутся без изменений.  
  
 Вызывайте эту функцию при использовании реализации платформы новый файл и открытие файла необязательно.  
  
##  <a name="loadtemplate"></a>  CDocTemplate::LoadTemplate  
 Загружает ресурсы для данного `CDocTemplate` или производного класса.  
  
```  
virtual void LoadTemplate();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой, чтобы загрузить ресурсы для данного `CDocTemplate` или производного класса. Обычно он вызывается во время построения, за исключением того, если шаблон создается глобально. В этом случае вызов `LoadTemplate` откладывается до [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) вызывается.  
  
##  <a name="matchdoctype"></a>  CDocTemplate::MatchDocType  
 Определяет степень уверенности в соответствие между типом документа и этот шаблон.  
  
```  
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,  
    CDocument*& rpDocMatch);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPathName`  
 Путь файла, тип которого определяется.  
  
 `rpDocMatch`  
 Указатель на документ, который назначается соответствующий документ, если файл, указанный параметром `lpszPathName` уже открыт.  
  
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
 Эту функцию можно используйте для определения типа документа шаблон, используемый для открытия файла. Если приложение поддерживает несколько типов файлов, например, вы эта функция используется для определения, какой из шаблонов документов доступны подходит для данного файла путем вызова `MatchDocType` для каждого шаблона в очередь, а затем выберите шаблон в соответствии с Возвращаемое значение достоверности.  
  
 Если файл, указанный параметром `lpszPathName` еще открыт, эта функция возвращает **CDocTemplate::yesAlreadyOpen** и копирует файл **CDocument** объект в объект с `rpDocMatch`.  
  
 Если файл не открыт, но с расширением в `lpszPathName` совпадает с расширением, заданным по **CDocTemplate::filterExt**, эта функция возвращает **CDocTemplate::yesAttemptNative** и задает `rpDocMatch` для **NULL**. Дополнительные сведения о **CDocTemplate::filterExt**, в разделе [CDocTemplate::GetDocString](#getdocstring).  
  
 Если ни одна из верно, функция возвращает **CDocTemplate::yesAttemptForeign**.  
  
 Реализация по умолчанию не возвращает **CDocTemplate::maybeAttemptForeign** или **CDocTemplate::maybeAttemptNative**. Переопределить эту функцию для реализации логики сопоставление типов соответствующий приложению, возможно с помощью этих двух значений из **достоверности** перечисления.  
  
##  <a name="opendocumentfile"></a>  Функции  
 Открывает файл, указанном путем.  
  
```  
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;  
 
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPathName`  
 Указатель на путь к файлу, содержащему открываемого документа.  
  
 [in] `bAddToMRU`  
 `TRUE` Указывает, что документ является одним из самых последних версий файлов; `FALSE` указывает документ не является одним из самых последних версий файлов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, названный файл которого `lpszPathName`; `NULL` в случае неудачи.  
  
### <a name="remarks"></a>Примечания  
 Открывает файл, путь которого задается `lpszPathName`. Если `lpszPathName` — `NULL`, создается новый файл, содержащий документ, тип которого связан с этим шаблоном.  
  
##  <a name="removedocument"></a>  CDocTemplate::RemoveDocument  
 Удаляет документ, на который указывает `pDoc` из списка документы, связанные с этим шаблоном.  
  
```  
virtual void RemoveDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Указатель на документ, который нужно удалить.  
  
### <a name="remarks"></a>Примечания  
 Производные классы `CMultiDocTemplate` и `CSingleDocTemplate` переопределить эту функцию. При наследовании класса шаблона документа из `CDocTemplate`, эту функцию необходимо переопределить производный класс.  
  
##  <a name="saveallmodified"></a>  CDocTemplate::SaveAllModified  
 Сохранение всех документов, которые были изменены.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; в противном случае — 0.  
  
##  <a name="setcontainerinfo"></a>  CDocTemplate::SetContainerInfo  
 Определяет ресурсы для OLE-контейнеры, при редактировании объекта OLE на месте.  
  
```  
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDOleInPlaceContainer`  
 Идентификатор ресурсы, используемые при активации внедренный объект.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию для задания ресурсов, которые будут использоваться при активации на месте объекта OLE. Эти ресурсы включают меню и таблицы сочетаний клавиш. Эта функция обычно вызывается [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) функции приложения.  
  
 Меню, связанное с `nIDOleInPlaceContainer` содержит разделители, позволяющие меню активированного элемента на месте для слияния с помощью меню приложения-контейнера. Дополнительные сведения о слиянии меню сервера и контейнера см. в статье [меню и ресурсы (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="setdefaulttitle"></a>  CDocTemplate::SetDefaultTitle  
 Эта функция вызывается для загрузки по умолчанию заголовок документа и отображения в строке заголовка документа.  
  
```  
virtual void SetDefaultTitle(CDocument* pDocument) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 *pDocument*  
 Указатель на документ, для которого заголовок задается.  
  
### <a name="remarks"></a>Примечания  
 Сведения о заголовок по умолчанию, см. в описании **CDocTemplate::docName** в [CDocTemplate::GetDocString](#getdocstring).  
  
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
 *nIDOleEmbedding*  
 Идентификатор ресурсы, используемые при открытии связанного объекта в отдельном окне.  
  
 `nIDOleInPlaceServer`  
 Идентификатор ресурсы, используемые при внедренный объект активации на месте.  
  
 *pOleFrameClass*  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, содержащую сведения о классе для объекта окна фрейма, созданного при активации на месте.  
  
 *pOleViewClass*  
 Указатель на `CRuntimeClass` структуру, содержащую сведения о классе для представления объекта, созданного при активации на месте.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для идентификации ресурсов, которые будут использоваться для приложения сервера при запросе активации внедренного объекта. Эти ресурсы включают меню и таблицы сочетаний клавиш. Эта функция обычно вызывается `InitInstance` приложения.  
  
 Меню, связанное с `nIDOleInPlaceServer` содержит разделители, позволяющие меню сервер для слияния с помощью меню контейнера. Дополнительные сведения о слиянии меню сервера и контейнера см. в статье [меню и ресурсы (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="createpreviewframe"></a>  CDocTemplate::CreatePreviewFrame  
 Создает дочерний кадр, используемый для расширенного просмотра.  
  
```  
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительское окно (обычно предоставляемых оболочкой).  
  
 `pDoc`  
 Указатель на объект документа, содержимое которых будет просматриваться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель на `CFrameWnd` объекта, или `NULL` сбоя создания.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpreviewinfo"></a>  CDocTemplate::SetPreviewInfo  
 Устанавливает внешней процесс обработчика предварительного просмотра.  
  
```  
void SetPreviewInfo(
    UINT nIDPreviewFrame,  
    CRuntimeClass* pPreviewFrameClass = NULL,  
    CRuntimeClass* pPreviewViewClass = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDPreviewFrame`  
 Указывает идентификатор ресурса кадра предварительного просмотра.  
  
 `pPreviewFrameClass`  
 Задает указатель на структуру сведения класса среды выполнения кадра предварительного просмотра.  
  
 `pPreviewViewClass`  
 Задает указатель на структуру сведений класса среды выполнения Предварительный просмотр.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md)   
 [Класс CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument-класс](../../mfc/reference/cdocument-class.md)   
 [CView-класс](../../mfc/reference/cview-class.md)   
 [Класс CScrollView](../../mfc/reference/cscrollview-class.md)   
 [Класс CEditView](../../mfc/reference/ceditview-class.md)   
 [Класс CFormView](../../mfc/reference/cformview-class.md)   
 [CFrameWnd-класс](../../mfc/reference/cframewnd-class.md)   
 [Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)
