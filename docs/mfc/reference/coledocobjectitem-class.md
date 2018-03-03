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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 246c645dad5ed11fb5428e2f90ed9b9574696417
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coledocobjectitem-class"></a>Класс COleDocObjectItem
Реализует хранение активных документов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|Создает `COleDocObject` элемента.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|Для печати из приложения контейнера с использованием параметров принтера по умолчанию.|  
|[COleDocObjectItem::ExecCommand](#execcommand)|Выполняет команду, заданное пользователем.|  
|[COleDocObjectItem::GetActiveView](#getactiveview)|Извлекает активное представление документа.|  
|[COleDocObjectItem::GetPageCount](#getpagecount)|Возвращает число страниц в приложение контейнера документа.|  
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|Подготавливает приложение контейнера документа для печати.|  
|[COleDocObjectItem::OnPrint](#onprint)|Для печати из приложения контейнера.|  
|[COleDocObjectItem::QueryCommand](#querycommand)|Запрашивает состояние одной или нескольких команд, созданных событиями пользовательского интерфейса.|  
|[COleDocObjectItem::Release](#release)|Освобождает соединение для связанного элемента OLE и закрывает его, если он был открыт. Уничтожает клиентский элемент.|  
  
## <a name="remarks"></a>Примечания  
 В MFC активного документа (regular), на месте для редактирования внедрение, со следующими отличиями обрабатывается точно так же:  
  
-   `COleDocument`-Производный класс по-прежнему ведет список элементов в данный момент embedded; тем не менее, это могут быть `COleDocObjectItem`-элементы, производные.  
  
-   При включенном активного документа занимает всю клиентскую область представления при активен на месте.  
  
-   Контейнер активного документа имеет полный контроль над **справки** меню.  
  
-   **Справки** меню содержит пункты меню для активного документа контейнера и сервера.  
  
 Поскольку контейнер активных документов владеет **справки** меню контейнера отвечает за сервера пересылки **справки** меню сообщения на сервер. Такая интеграция обрабатывается `COleDocObjectItem`.  
  
 Дополнительные сведения о слияния меню и активации активный документ. в разделе Обзор [вложение активного документа](../../mfc/active-document-containment.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="coledocobjectitem"></a>COleDocObjectItem::COleDocObjectItem  
 Вызовите эту функцию-член для инициализации `COleDocObjectItem` объекта.  
  
```  
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pContainerDoc`  
 Указатель на `COleDocument` объект выступает в роли контейнера активного документа. Этот параметр должен быть **NULL** для включения **IMPLEMENT_SERIALIZE**. Обычно элементы OLE создаются с не поддерживающими **NULL** указатель документа.  
  
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
 Указатель на [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) объекта, который описывает задание на печать.  
  
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
 Идентификатор команды для выполнения. Должен находиться в группе, определенной `pguidCmdGroup`.  
  
 `nCmdExecOpt`  
 Указывает параметры выполнения команды. По умолчанию значение для выполнения команды без запроса пользователя. В разделе [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) список значений.  
  
 `pguidCmdGroup`  
 Уникальный идентификатор группы команд. По умолчанию **NULL**, который указывает стандартные группы. Команда переданный `nCmdID` должен принадлежать к группе.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` в случае успешного выполнения; в противном случае возвращает с одним из следующих кодов ошибки.  
  
|Значение|Описание:|  
|-----------|-----------------|  
|**E_UNEXPECTED**|Произошла непредвиденная ошибка.|  
|**E_FAIL**|Произошла ошибка.|  
|**E_NOTIMPL**|Указывает MFC сам следует попытаться перевести и отправляет команду.|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`не является **NULL** , но не указана группа распознано в качестве команды.|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`не является допустимой команды в pGroup группы.|  
|**OLECMDERR_DISABLED**|Команду по `nCmdID` отключена и не может быть выполнена.|  
|**OLECMDERR_NOHELP**|Вызывающий объект запрашивает справки на команду по `nCmdID` , но Справка недоступна.|  
|**OLECMDERR_CANCELLED**|Выполнение отменено пользователем.|  
  
### <a name="remarks"></a>Примечания  
 `pguidCmdGroup` И `nCmdID` параметров, которые совместно однозначно идентифицируют команду, вызываемую. `nCmdExecOpt` Указывает точное предпринять действия.  
  
##  <a name="getactiveview"></a>COleDocObjectItem::GetActiveView  
 Вызовите эту функцию-член для получения указателя на `IOleDocumentView` интерфейс активного представления.  
  
```  
LPOLEDOCUMENTVIEW GetActiveView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [IOleDocumentView](http://msdn.microsoft.com/library/windows/desktop/ms678455) интерфейс активного представления. Если нет текущего представления, он возвращает **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Счетчик ссылок для полученного `IOleDocumentView` указатель не увеличивается, возвращаемую этой функцией.  
  
##  <a name="getpagecount"></a>COleDocObjectItem::GetPageCount  
 Вызовите эту функцию-член для извлечения номера страниц в документе.  
  
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
 Эта функция-член вызывается платформой для подготовки для печати документа.  
  
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
 Указатель на [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) объекта, который описывает задание на печать.  
  
 `bPrintAll`  
 Указывает, является ли на печать всего документа.  
  
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
 Указатель на [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) объекта, который описывает задание на печать.  
  
 `bPrintAll`  
 Указывает, является ли на печать всего документа.  
  
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
 Указатель на флажки, возвращаемые в результате запроса. Список возможных значений см. в разделе [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237).  
  
 `pCmdText`  
 Указатель на [OLECMDTEXT](http://msdn.microsoft.com/library/windows/desktop/ms693314) структуры, в которой для возврата сведений о имя и состояние для одной команды. Может быть **NULL** для указания, что ему нужны эти сведения.  
  
 `pguidCmdGroup`  
 Уникальный идентификатор группы команд; может быть **NULL** для указания стандартной группы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полный список возвращаемых значений см. в разделе [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) метода, как описано в Windows SDK.  
  
##  <a name="release"></a>COleDocObjectItem::Release  
 Освобождает соединение для связанного элемента OLE и закрывает его, если он был открыт. Уничтожает клиентский элемент.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCloseOption`  
 Флаг, указывающий, при каких обстоятельствах объекта OLE сохраняется при возвращении в загруженное состояние. Список возможных значений см. в разделе [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close).  
  
### <a name="remarks"></a>Примечания  
 Уничтожает клиентский элемент.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MFCBIND](../../visual-cpp-samples.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Класс CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)
