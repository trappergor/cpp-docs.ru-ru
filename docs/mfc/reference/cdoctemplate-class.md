---
title: "CDocTemplate-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- document templates
- templates, document
- CDocTemplate class
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
caps.latest.revision: 22
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
ms.openlocfilehash: 56ad45a061986c320e14054a2c77683cb5d89ac2
ms.lasthandoff: 02/24/2017

---
# <a name="cdoctemplate-class"></a>CDocTemplate-класс
Абстрактный базовый класс, который определяет базовую функциональность шаблонов документов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
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
|[CDocTemplate::CreateNewFrame](#createnewframe)|Создает новый рамка окна, содержащего документа и представления.|  
|[CDocTemplate::CreateOleFrame](#createoleframe)|Создает окно кадров, поддержкой OLE.|  
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|Создает дочерний кадр, используемый для расширенного просмотра.|  
|[CDocTemplate::GetDocString](#getdocstring)|Возвращает строку, связанную с типом документа.|  
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|Возвращает позицию первого документа, связанного с этим шаблоном.|  
|[CDocTemplate::GetNextDoc](#getnextdoc)|Получает документ и положение следующего.|  
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|Инициализирует фрейма окна и при необходимости сделает ее видимой.|  
|[CDocTemplate::LoadTemplate](#loadtemplate)|Загружает ресурсы для данного `CDocTemplate` или производного класса.|  
|[CDocTemplate::MatchDocType](#matchdoctype)|Определяет степень уверенности в соответствие типа документа и этот шаблон.|  
|[Функции](#opendocumentfile)|Открывает файл, указанный параметром pathname.|  
|[CDocTemplate::RemoveDocument](#removedocument)|Удаляет документ из шаблона.|  
|[CDocTemplate::SaveAllModified](#saveallmodified)|Сохраняет все документы, связанные с помощью этого шаблона, которые были изменены.|  
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|Определяет ресурсы для OLE-контейнеры, при редактировании объекта OLE на месте.|  
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|Заголовка по умолчанию отображается в строке заголовка окна документа.|  
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|Параметры настройки из обработчика просмотра процесса.|  
|[CDocTemplate::SetServerInfo](#setserverinfo)|Определяет ресурсы и классы, если серверный документ внедрен или редактирования на месте.|  
  
## <a name="remarks"></a>Примечания  
 Обычно создается один или несколько шаблонов документов в реализации приложения `InitInstance` функции. Шаблон документа определяет отношения между три типа классов:  
  
-   Класс документа, который необходимо наследовать от **CDocument**.  
  
-   Класс представления отображает данные из класса документа, перечисленных выше. Можно наследовать этот класс из `CView`, `CScrollView`, `CFormView`, или `CEditView`. (Можно также использовать `CEditView` напрямую.)  
  
-   Класс фрейм окна, который содержит представление. Однооконный интерфейс (SDI) приложения, являются производными от этого класса `CFrameWnd`. Для нескольких приложений интерфейса (MDI) документа, необходимо наследовать от этого класса `CMDIChildWnd`. Если не нужно настраивать поведение окна фрейма, можно использовать `CFrameWnd` или `CMDIChildWnd` напрямую без создания собственного производного класса.  
  
 Приложение имеет один шаблон документа для каждого типа документа, который он поддерживает. Например если приложение поддерживает электронных таблиц и текстовых документов, приложение имеет два объекта шаблона документа. Каждый шаблон документа отвечает за создание и управление ими все документы этого типа.  
  
 Шаблон документа хранит указатели на `CRuntimeClass` объектов для документов, представления и классы окна фрейма. Эти `CRuntimeClass` объекты, указанные при создании шаблона документа.  
  
 Шаблон документа содержит идентификатор ресурсы, используемые с типом документа (например, меню, значок или ресурсами таблицы сочетаний клавиш). Шаблон документа имеются строки, содержащие дополнительные сведения о его тип документа. К ним относятся имя типа документа (например, «лист») и расширение файла (например, «.xls»). При необходимости он может содержать другие строки, используется интерфейс пользователя, диспетчер файлов и связывания объектов и поддержка внедрения (OLE).  
  
 Если приложение является OLE-контейнер, или сервера, шаблон документа также определяет идентификатор меню, которое используется во время активации на месте. Если приложение является OLE-сервер, шаблон документа определяет идентификатор панели инструментов и меню, которое используется во время активации на месте. Укажите эти дополнительные ресурсы OLE путем вызова `SetContainerInfo` и `SetServerInfo`.  
  
 Поскольку `CDocTemplate` является абстрактным классом, класс нельзя использовать напрямую. Типичное приложение использует один из двух `CDocTemplate`-производных классов, предоставляемых библиотеки классов Microsoft Foundation: `CSingleDocTemplate`, который реализует SDI, и `CMultiDocTemplate`, который реализует MDI. В разделе этих классов для получения дополнительной информации об использовании шаблонов документов.  
  
 Если приложению требуется пользовательский интерфейс парадигмы, существенно отличается от SDI или интерфейса MDI, можно наследовать класс из `CDocTemplate`.  
  
 Дополнительные сведения о `CDocTemplate`, в разделе [шаблоны документов и процесс создания документов и представлений](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="adddocument"></a>CDocTemplate::AddDocument  
 Эта функция используется для добавления документа в шаблон.  
  
```  
virtual void AddDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Указатель должен быть добавлен в документ.  
  
### <a name="remarks"></a>Примечания  
 Производные классы [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) и [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) переопределить эту функцию. При наследовании класса шаблона документа из `CDocTemplate`, производный класс должен переопределить эту функцию.  
  
##  <a name="cdoctemplate"></a>CDocTemplate::CDocTemplate  
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
 Указывает идентификатор ресурсов, используемых с типом документа. Это может включать меню, значок, таблицы сочетаний клавиш и строковые ресурсы.  
  
 Строковый ресурс состоит из до семи подстрок, разделенных символом «\n» (символ «\n» требуется как местозаполнитель, если подстрока не включено; тем не менее, конечные символы «\n» не обязательны); Эти подстроки описания типа документа. Сведения о подстроках разделе [GetDocString](#getdocstring). Этот строковый ресурс находится в файле ресурсов приложения. Например:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Обратите внимание, что строка начинается со знака «\n»; Это вызвано первую подстроку не используется в приложениях MDI и поэтому не включено. Можно изменить эту строку в редакторе строк; вся строка представляется как одна запись в редакторе строк не семь отдельные записи.  
  
 `pDocClass`  
 Указывает `CRuntimeClass` объекта класса документа. Этот класс является **CDocument**-производный класс, определенный для представления документов.  
  
 `pFrameClass`  
 Указывает `CRuntimeClass` объекта класс фреймового окна. Этот класс может быть `CFrameWnd`-производного класса, или он может быть `CFrameWnd` себя, если требуется поведение по умолчанию для главного окна фрейма.  
  
 `pViewClass`  
 Указывает `CRuntimeClass` объекта класса представления. Этот класс является `CView`-производного класса можно определить для отображения документов.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член для создания `CDocTemplate` объекта. Динамически выделять `CDocTemplate` объект и передать его в [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) из `InitInstance` функции-члена класса приложения.  
  
##  <a name="closealldocuments"></a>CDocTemplate::CloseAllDocuments  
 Вызовите эту функцию-член, чтобы закрыть все открытые документы.  
  
```  
virtual void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Параметры  
 `bEndSession`  
 Указывает, является ли окончания сеанса. Это **TRUE** Если сеанс завершается; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член обычно используется как часть команды файл выхода. Реализация по умолчанию эта функция вызывает [CDocument::DeleteContents](../../mfc/reference/cdocument-class.md#deletecontents) функция-член для удаления документа данных, а затем закрывает окна фрейма для всех представлений, прикрепленной к документу.  
  
 Эту функцию можно переопределите, чтобы требовать от пользователя для выполнения специальной очистки обработки до закрытия документа. Например документ представляет запись в базе данных, можно переопределить эту функцию для закрытия базы данных.  
  
##  <a name="createnewdocument"></a>CDocTemplate::CreateNewDocument  
 Вызов этой функции-члена для создания документа типа, связанного с этим шаблоном документа.  
  
```  
virtual CDocument* CreateNewDocument();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданного документа или **NULL** при возникновении ошибки.  
  
##  <a name="createnewframe"></a>CDocTemplate::CreateNewFrame  
 Создает новый рамка окна, содержащего документа и представления.  
  
```  
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,  
    CFrameWnd* pOther);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Документ, на которые должна ссылаться нового окна области. Может быть **NULL**.  
  
 `pOther`  
 Окна фрейма, на которой будет основываться нового окна области. Может быть **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный фрейме окна, или **NULL** при возникновении ошибки.  
  
### <a name="remarks"></a>Примечания  
 `CreateNewFrame`использует `CRuntimeClass` объекты передаются в конструктор для создания нового окна области представление и вложенный документ. Если `pDoc` параметр **NULL**, платформа выводит сообщение ТРАССИРОВКИ.  
  
 `pOther` Параметр используется для реализации окно Новая команда. Он предоставляет окно, в котором для моделирования нового окна области. Обычно создается невидимым нового окна области. Эта функция вызывается для создания окна фрейма вне Стандартная реализация структуры новых файлов и открытие файла.  
  
##  <a name="createoleframe"></a>CDocTemplate::CreateOleFrame  
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
 Указатель на документ, на которые должна ссылаться нового окна области OLE.  
  
 `bCreateView`  
 Определяет, создается ли представление и рамки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на фрейм окна, в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если `bCreateView` равен нулю, создается пустая рамка.  
  
##  <a name="getdocstring"></a>CDocTemplate::GetDocString  
 Возвращает строку, связанную с типом документа.  
  
```  
virtual BOOL GetDocString(
    CString& rString,  
    enum DocStringIndex index) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rString`  
 Ссылку на `CString` объект, который будет содержать строку, когда функция возвращает значение.  
  
 *Индекс*  
 Индекс подстроки, извлекаемых из строка, описывающая тип документа. Этот параметр может принимать одно из следующих значений:  
  
- **CDocTemplate::windowTitle** имя, которое отображается в строке (например, «Microsoft Excel») заголовка окна приложения. Присутствующие только в шаблоне документа для SDI-приложения.  
  
- **CDocTemplate::docName** корневого имени по умолчанию документ (например, «Таблицы»). Этим корнем, вместе с номером используется имя по умолчанию новый документ этого типа всякий раз, когда пользователь выбирает команду «New» из меню «файл» (например, «Лист1» или «Лист2»). Если не указано «Безымянный» используется по умолчанию.  
  
- **CDocTemplate::fileNewName** имя этого типа документа. Если приложение поддерживает несколько типов документов, эта строка отображается в диалоговом окне новый файл (например, «лист»). Если не указан, тип документа недоступен с помощью команды Создать файл.  
  
- **CDocTemplate::filterName** описание типа документа и соответствующих документов данного типа фильтра с подстановочными знаками. Эта строка отображается в раскрывающемся списке Тип файлов в диалоговом окне открытия файла (например, «листов (*.xls)»). Если не указан, тип документа недоступен с помощью команды открытия файла.  
  
- **CDocTemplate::filterExt** расширение для документов этого типа (например, «.xls»). Если не указан, тип документа недоступен с помощью команды открытия файла.  
  
- **CDocTemplate::regFileTypeId** идентификатор типа документа сохраняются в базе данных регистрации, поддерживаемый Windows. Эта строка представляет только для внутреннего использования (например, «ExcelWorksheet»). Если не указан, тип документа не регистрируются с помощью диспетчера файлов Windows.  
  
- **CDocTemplate::regFileTypeName** имя типа документа сохраняются в базе данных регистрации. Эта строка может отображаться в диалоговых окнах приложения, доступ к базе данных регистрации (например, «лист Microsoft Excel»).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если указанная подстрока, найдена; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения конкретной подстроки, описывающий тип документа. Строка, содержащая эти подстроки хранится в шаблоне документа и является производным от строки в файле ресурсов для приложения. Платформа вызывает эту функцию для получения строки, необходимые для пользовательского интерфейса приложения. При указании расширения имени файла для документов в приложении платформа также вызывает эту функцию при добавлении записи в базу данных регистрации Windows. Это позволяет документы будут открываться в диспетчере файлов Windows.  
  
 Эта функция вызывается только в том случае, если вы сделаете производный класс от `CDocTemplate`.  
  
##  <a name="getfirstdocposition"></a>CDocTemplate::GetFirstDocPosition  
 Возвращает позицию первого документа, связанного с этим шаблоном.  
  
```  
virtual POSITION GetFirstDocPosition() const = 0;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации по списку документов, связанных с этим шаблоном документа; или **NULL** Если список пуст.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для получения позиции первого документа в список документов, связанных с данным шаблоном. Используйте **ПОЗИЦИИ** значение в качестве аргумента [CDocTemplate::GetNextDoc](#getnextdoc) для итерации по списку документов, связанных с шаблоном.  
  
 [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) и [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) обоих переопределить это чисто виртуальную функцию. Любой класс, производный от `CDocTemplate` необходимо также переопределить эту функцию.  
  
##  <a name="getnextdoc"></a>CDocTemplate::GetNextDoc  
 Получает элемент списка, определенный `rPos`, затем устанавливает `rPos` для **ПОЗИЦИИ** значение следующей записи в списке.  
  
```  
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на следующий документ в список документов, связанных с данным шаблоном.  
  
### <a name="parameters"></a>Параметры  
 `rPos`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим вызовом [GetFirstDocPosition](#getfirstdocposition) или `GetNextDoc`.  
  
### <a name="remarks"></a>Примечания  
 Если полученный элемент является последним в списке, то новое значение `rPos` равен **NULL**.  
  
 Можно использовать `GetNextDoc` в прямой итерации цикла, если установить начальное положение, с помощью вызова [GetFirstDocPosition](#getfirstdocposition).  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** значение представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
##  <a name="initialupdateframe"></a>CDocTemplate::InitialUpdateFrame  
 Инициализирует фрейма окна и при необходимости сделает ее видимой.  
  
```  
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,  
    CDocument* pDoc,  
    BOOL bMakeVisible = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pFrame`  
 Окно фрейма, нужно обновить начальной.  
  
 `pDoc`  
 Документ, с которым связана кадра. Может быть **NULL**.  
  
 `bMakeVisible`  
 Указывает ли кадр станет видимым и активной.  
  
### <a name="remarks"></a>Примечания  
 Вызов **IntitialUpdateFrame** после создания новый кадр с `CreateNewFrame`. При вызове этой функции приводит представления, фрейм окна, чтобы получить их `OnInitialUpdate` вызовов. Кроме того Если существует не была ранее активное представление, основного представления окна фрейма делается активным; основное представление — это представление с ИД дочернего объекта **AFX_IDW_PANE_FIRST**. Наконец, будет виден в фрейме окна Если `bMakeVisible` значение не равно нулю. Если `bMakeVisible` равен нулю, текущим местоположением и видимое состояние окна фрейма остаются неизменными.  
  
 Эта функция вызывается при использовании платформы реализации новых файлов и открытие файла необязательно.  
  
##  <a name="loadtemplate"></a>CDocTemplate::LoadTemplate  
 Загружает ресурсы для данного `CDocTemplate` или производного класса.  
  
```  
virtual void LoadTemplate();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывается платформой для загрузки ресурсов для данной `CDocTemplate` или производного класса. Обычно он вызывается во время построения, за исключением при глобально сконструированный шаблон. В этом случае вызов `LoadTemplate` откладывается до [CWinApp::AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) вызывается.  
  
##  <a name="matchdoctype"></a>CDocTemplate::MatchDocType  
 Определяет степень уверенности в соответствие типа документа и этот шаблон.  
  
```  
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,  
    CDocument*& rpDocMatch);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPathName`  
 Путь файла, тип которого требуется определить.  
  
 `rpDocMatch`  
 Указатель на документ, который назначается соответствующий документ, если файл, указанный параметром `lpszPathName` уже открыт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение из **достоверности** перечисления, который определен следующим образом:  
  
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
 Эту функцию можно используйте для определения типа шаблона документа, который используется для открытия файла. Если приложение поддерживает несколько типов файлов, например, вы эта функция используется для определения шаблонов документов, доступных для данного файла путем вызова `MatchDocType` для каждого шаблона в очередь и выбрав шаблон согласно значению достоверности возвращаемых.  
  
 Если файл, указанный параметром `lpszPathName` будет уже открыт, эта функция возвращает **CDocTemplate::yesAlreadyOpen** и копирует файл **CDocument** в объект в `rpDocMatch`.  
  
 Если файл не открыт, но с расширением в `lpszPathName` соответствует расширение, указанное **CDocTemplate::filterExt**, эта функция возвращает **CDocTemplate::yesAttemptNative** и задает `rpDocMatch` для **NULL**. Дополнительные сведения о **CDocTemplate::filterExt**, в разделе [CDocTemplate::GetDocString](#getdocstring).  
  
 Если ни один случай имеет значение true, функция возвращает **CDocTemplate::yesAttemptForeign**.  
  
 Реализация по умолчанию не возвращает **CDocTemplate::maybeAttemptForeign** или **CDocTemplate::maybeAttemptNative**. Переопределить эту функцию, чтобы реализовать сопоставление типов логики, соответствующий приложению, возможно с помощью этих двух значений из **достоверности** перечисления.  
  
##  <a name="opendocumentfile"></a>Функции  
 Открытие файла в указанном пути.  
  
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
 `TRUE`Указывает, что документ является одним из самых последних версий файлов; `FALSE` указывает документ не является одним из самых последних версий файлов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на документ, названный файл которого `lpszPathName`; `NULL` в случае неудачи.  
  
### <a name="remarks"></a>Примечания  
 Открывает файл, путь которого задается `lpszPathName`. Если `lpszPathName` — `NULL`, создается новый файл, содержащий документа, тип, связанный с этим шаблоном.  
  
##  <a name="removedocument"></a>CDocTemplate::RemoveDocument  
 Удаляет документ, на который указывает `pDoc` в списке документов, связанных с этим шаблоном.  
  
```  
virtual void RemoveDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>Параметры  
 `pDoc`  
 Указатель на документ, должны быть удалены.  
  
### <a name="remarks"></a>Примечания  
 Производные классы `CMultiDocTemplate` и `CSingleDocTemplate` переопределить эту функцию. При наследовании класса шаблона документа из `CDocTemplate`, производный класс должен переопределить эту функцию.  
  
##  <a name="saveallmodified"></a>CDocTemplate::SaveAllModified  
 Сохранение всех документов, которые были изменены.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; в противном случае — 0.  
  
##  <a name="setcontainerinfo"></a>CDocTemplate::SetContainerInfo  
 Определяет ресурсы для OLE-контейнеры, при редактировании объекта OLE на месте.  
  
```  
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDOleInPlaceContainer`  
 Идентификатор ресурсы, используемые при активации внедренный объект.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для набор ресурсов, которые будут использоваться при активации на месте OLE-объекта. Эти ресурсы включают меню и таблицы сочетаний клавиш. Эта функция обычно вызывается [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) функции приложения.  
  
 Меню, связанное с `nIDOleInPlaceContainer` содержит разделители, позволяющие меню элемента активации на месте для слияния с меню приложения-контейнера. Дополнительные сведения об объединении меню сервера и контейнера см. в статье [меню и ресурсы (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="setdefaulttitle"></a>CDocTemplate::SetDefaultTitle  
 Эта функция вызывается для загрузки по умолчанию заголовок документа и его отображения в строке заголовка документа.  
  
```  
virtual void SetDefaultTitle(CDocument* pDocument) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 *pDocument*  
 Указатель на документ, чья должность имеет задать.  
  
### <a name="remarks"></a>Примечания  
 Сведения о заголовка по умолчанию, см. в описании **CDocTemplate::docName** в [CDocTemplate::GetDocString](#getdocstring).  
  
##  <a name="setserverinfo"></a>CDocTemplate::SetServerInfo  
 Определяет ресурсы и классы, если серверный документ внедрен или редактирования на месте.  
  
```  
void SetServerInfo(
    UINT nIDOleEmbedding,  
    UINT nIDOleInPlaceServer = 0,  
    CRuntimeClass* pOleFrameClass = NULL,  
    CRuntimeClass* pOleViewClass = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDOleEmbedding*  
 Идентификатор ресурсы, используемые при открытии внедренный объект в отдельном окне.  
  
 `nIDOleInPlaceServer`  
 Идентификатор ресурсов, используемых при внедренный объект активации на месте.  
  
 *pOleFrameClass*  
 Указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) структуру, содержащую сведения о классах для объект окна фрейма, созданный при активации на месте.  
  
 *pOleViewClass*  
 Указатель на `CRuntimeClass` структуру, содержащую сведения класса для объекта представления, созданные при активации на месте.  
  
### <a name="remarks"></a>Примечания  
 Вызовите эту функцию-член для идентификации ресурсов, которые будут использоваться для приложения сервера при запросе активации внедренный объект. Эти ресурсы включают меню и таблицы сочетаний клавиш. Эта функция обычно вызывается `InitInstance` приложения.  
  
 Меню, связанное с `nIDOleInPlaceServer` содержит разделители, позволяющие меню сервера для слияния с помощью меню контейнера. Дополнительные сведения об объединении меню сервера и контейнера см. в статье [меню и ресурсы (OLE)](../../mfc/menus-and-resources-ole.md).  
  
##  <a name="createpreviewframe"></a>CDocTemplate::CreatePreviewFrame  
 Создает дочерний кадр, используемый для расширенного просмотра.  
  
```  
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentWnd`  
 Указатель на родительское окно (обычно предоставляется оболочка).  
  
 `pDoc`  
 Указатель на объект документа, содержимое которых будет просматриваться.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель на `CFrameWnd` объекта, или `NULL` в случае сбоя создания.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setpreviewinfo"></a>CDocTemplate::SetPreviewInfo  
 Устанавливает вне процесса обработчика просмотра.  
  
```  
void SetPreviewInfo(
    UINT nIDPreviewFrame,  
    CRuntimeClass* pPreviewFrameClass = NULL,  
    CRuntimeClass* pPreviewViewClass = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDPreviewFrame`  
 Указывает идентификатор ресурса для окна предварительного просмотра.  
  
 `pPreviewFrameClass`  
 Задает указатель на структуру сведения класса среды выполнения окна предварительного просмотра.  
  
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
 [CMDIChildWnd-класс](../../mfc/reference/cmdichildwnd-class.md)

