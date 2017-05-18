---
title: "Класс COleDocObjectItem | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- COleDocObjectItem class
- document object containment
- containment
- containment, doc object
- doc object containment
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0815454fa4b194e97a2d16a621cfc25da61d5fd0
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="coledocobjectitem-class"></a>Класс COleDocObjectItem
Реализует хранение активных документов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Создает `COleDocObject` элемента.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Для печати приложения-контейнера с использованием параметров принтера по умолчанию.|  
|[COleDocObjectItem::ExecCommand](#execcommand)|Выполняет команды, заданные пользователем.|  
|[COleDocObjectItem::GetActiveView](#getactiveview)|Возвращает представление активного документа.|  
|[COleDocObjectItem::GetPageCount](#getpagecount)|Возвращает число страниц в документе приложения-контейнера.|  
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|Подготавливает приложения-контейнера документа для печати.|  
|[COleDocObjectItem::OnPrint](#onprint)|Приложения-контейнера для печати.|  
|[COleDocObjectItem::QueryCommand](#querycommand)|Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.|  
|[COleDocObjectItem::Release](#release)|Освобождает соединение для связанного элемента OLE и закрывает его, если он был открыт. Не разрушает клиентский элемент.|  
  
## <a name="remarks"></a>Примечания  
 В MFC активный документ подобным образом распределяется обычный, на месте для редактирования внедрения, со следующими отличиями:  
  
-   `COleDocument`-Производный класс по-прежнему ведет список внедренных в настоящее время элементов; тем не менее, эти элементы могут быть `COleDocObjectItem`-элементы, производные.  
  
-   Активный документ активен, занимает всю клиентскую область представления, когда активен на месте.  
  
-   Контейнер активного документа имеет полный контроль над **помочь** меню.  
  
-   **Помочь** меню содержит пункты для контейнера активных документов и сервера.  
  
 Поскольку контейнер активных документов владеет **помочь** меню контейнера отвечает за сервера пересылки **помочь** меню сообщения на сервер. Такая интеграция обрабатывается `COleDocObjectItem`.  
  
 Дополнительные сведения о слияния меню и активации активного документа в разделе Общие сведения о [вложение активного документа](../../mfc/active-document-containment.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coledocobjectitem"></a>COleDocObjectItem::COleDocObjectItem  
 Вызов этой функции-члена для инициализации `COleDocObjectItem` объекта.  
  
```  
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pContainerDoc`  
 Указатель на `COleDocument` объект выступает в качестве контейнера активных документов. Этот параметр должен быть **NULL** для включения **IMPLEMENT_SERIALIZE**. Обычно OLE-элементы создаются с не поддерживающими **NULL** указатель документа.  
  
##  <a name="dodefaultprinting"></a>COleDocObjectItem::DoDefaultPrinting  
 Вызывается платформой для документа, используя параметры по умолчанию.  
  
```  
static HRESULT DoDefaultPrinting(
    CView* pCaller,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `pCaller`  
 Указатель на [CView](../../mfc/reference/cview-class.md) объект, который отправляет команды print.  
  
 `pInfo`  
 Указатель на [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) объект, который содержит описание задания печати.  
  
##  <a name="execcommand"></a>COleDocObjectItem::ExecCommand  
 Вызовите эту функцию-член для выполнения команды, заданные пользователем.  
  
```  
HRESULT ExecCommand(
    DWORD nCmdID,  
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,  
    const GUID* pguidCmdGroup = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nCmdID`  
 Идентификатор выполнения команды. Должен находиться в группе, определенной `pguidCmdGroup`.  
  
 `nCmdExecOpt`  
 Указывает параметры выполнения команды. По умолчанию, выполните команду без подтверждения пользователя. В разделе [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) список значений.  
  
 `pguidCmdGroup`  
 Уникальный идентификатор группы команд. По умолчанию **NULL**, который указывает стандартные группы. Команда передается в `nCmdID` должен принадлежать к группе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` в случае успешного выполнения; в противном случае — возвращает с одним из следующих кодов ошибки.  
  
|Значение|Описание|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Произошла непредвиденная ошибка.|  
|**E_FAIL**|Произошла ошибка.|  
|**E_NOTIMPL**|Указывает MFC сам должен попытаться перевести и распределения команды.|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`не **NULL** , но не указана группа распознано в качестве команды.|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`не является допустимой команды в группу pGroup.|  
|**OLECMDERR_DISABLED**|Команда, идентифицируемый `nCmdID` отключена и не может быть выполнена.|  
|**OLECMDERR_NOHELP**|Вызывающий объект запрашивает справки о команде, определяемый `nCmdID` , но Справка недоступна.|  
|**OLECMDERR_CANCELLED**|Выполнение отменено пользователем.|  
  
### <a name="remarks"></a>Примечания  
 `pguidCmdGroup` И `nCmdID` параметры вместе уникально идентифицировать вызываемой команды. `nCmdExecOpt` Параметр указывает точное действие.  
  
##  <a name="getactiveview"></a>COleDocObjectItem::GetActiveView  
 Вызов этой функции-члена для получения указателя на `IOleDocumentView` интерфейс активного представления.  
  
```  
LPOLEDOCUMENTVIEW GetActiveView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [IOleDocumentView](http://msdn.microsoft.com/library/windows/desktop/ms678455) интерфейс активного представления. Если нет текущего представления, она возвращает **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Счетчик ссылок для возвращенного `IOleDocumentView` указатель не увеличивается, возвращаемую этой функцией.  
  
##  <a name="getpagecount"></a>COleDocObjectItem::GetPageCount  
 Вызовите эту функцию-член для получения числа страниц в документе.  
  
```  
BOOL GetPageCount(
    LPLONG pnFirstPage,  
    LPLONG pcPages);
```  
  
### <a name="parameters"></a>Параметры  
 *pnFirstPage*  
 Указатель на номер первой страницы документа. Может быть **NULL**, указывает, вызывающий этот номер не требуется.  
  
 *pcPages*  
 Указатель на общее число страниц в документе. Может быть **NULL**, указывает, вызывающий этот номер не требуется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="onprepareprinting"></a>COleDocObjectItem::OnPreparePrinting  
 Эта функция-член вызывается платформой для подготовки к печати документа.  
  
```  
static BOOL OnPreparePrinting(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pCaller`  
 Указатель на [CView](../../mfc/reference/cview-class.md) объект, который отправляет команды print.  
  
 `pInfo`  
 Указатель на [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) объект, который содержит описание задания печати.  
  
 `bPrintAll`  
 Указывает, является ли весь документ для печати.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="onprint"></a>COleDocObjectItem::OnPrint  
 Эта функция-член вызывается платформой для печати документа.  
  
```  
static void OnPrint(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `pCaller`  
 Указатель на объект CView, который отправляет команды print.  
  
 `pInfo`  
 Указатель на [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) объект, который содержит описание задания печати.  
  
 `bPrintAll`  
 Указывает, является ли весь документ для печати.  
  
##  <a name="querycommand"></a>COleDocObjectItem::QueryCommand  
 Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.  
  
```  
HRESULT QueryCommand(
    ULONG nCmdID,  
    DWORD* pdwStatus,  
    OLECMDTEXT* pCmdText =NULL,  
    const GUID* pguidCmdGroup =NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nCmdID`  
 Идентификатор команды, для которого запрашивается.  
  
 `pdwStatus`  
 Указатель флаги, возвращаемых в результате запроса. Список возможных значений см. в разделе [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237).  
  
 `pCmdText`  
 Указатель на [OLECMDTEXT](http://msdn.microsoft.com/library/windows/desktop/ms693314) структуру, в которой для возврата сведений о имя и состояние для отдельной команды. Может быть **NULL** для указания, что ему нужны эти сведения.  
  
 `pguidCmdGroup`  
 Уникальный идентификатор группы команд; может быть **NULL** для указания стандартной группы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный список возвращаемых значений в разделе [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) метода, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="release"></a>COleDocObjectItem::Release  
 Освобождает соединение для связанного элемента OLE и закрывает его, если он был открыт. Не разрушает клиентский элемент.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCloseOption`  
 Флаг, указывающий, при каких обстоятельствах объекта OLE сохраняется при возвращении в загруженное состояние. Список возможных значений см. в разделе [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close).  
  
### <a name="remarks"></a>Примечания  
 Не разрушает клиентский элемент.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MFCBIND](../../visual-cpp-samples.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Класс CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)

