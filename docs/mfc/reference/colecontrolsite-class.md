---
title: Класс COleControlSite | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
dev_langs:
- C++
helpviewer_keywords:
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61544026f559e0c45cbd81735e76203a088d2d6b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040877"
---
# <a name="colecontrolsite-class"></a>Класс COleControlSite
Обеспечивает поддержку пользовательских интерфейсов клиентских элементов управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlSite::COleControlSite](#colecontrolsite)|Создает объект `COleControlSite`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|Привязывает свойство по умолчанию размещенного элемента управления к источнику данных.|  
|[COleControlSite::BindProperty](#bindproperty)|Привязывает свойство размещенного элемента управления к источнику данных.|  
|[COleControlSite::CreateControl](#createcontrol)|Создает размещенный элемент управления ActiveX.|  
|[COleControlSite::DestroyControl](#destroycontrol)|Уничтожает размещенного элемента управления.|  
|[COleControlSite::DoVerb](#doverb)|Выполняет определенные команды размещенного элемента управления.|  
|[COleControlSite::EnableDSC](#enabledsc)|Включение данных источники для узла элемента управления.|  
|[COleControlSite::EnableWindow](#enablewindow)|Позволяет веб-элемента управления узла.|  
|[COleControlSite::FreezeEvents](#freezeevents)|Указывает, если узел элемента управления прием событий.|  
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Извлекает код кнопки по умолчанию для размещенного элемента управления.|  
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Получает идентификатор элемента управления.|  
|[COleControlSite::GetEventIID](#geteventiid)|Извлекает идентификатор интерфейс событий для размещенного элемента управления.|  
|[COleControlSite::GetExStyle](#getexstyle)|Извлекает расширенные стили элемента управления узла.|  
|[COleControlSite::GetProperty](#getproperty)|Извлекает указанное свойство размещенного элемента управления.|  
|[COleControlSite::GetStyle](#getstyle)|Извлекает стили элемента управления узла.|  
|[COleControlSite::GetWindowText](#getwindowtext)|Извлекает текст размещенного элемента управления.|  
|[COleControlSite::InvokeHelper](#invokehelper)|Вызова определенного метода размещенного элемента управления.|  
|[COleControlSite::InvokeHelperV](#invokehelperv)|Вызова определенного метода размещенного элемента управления с переменный список аргументов.|  
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Определяет, является ли элемент управления кнопкой по умолчанию в окне.|  
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Проверяет, видимое состояние сайта элемента управления.|  
|[COleControlSite::ModifyStyle](#modifystyle)|Изменяет текущий расширенные стили элемента управления узла.|  
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Изменяет стили текущего элемента управления узла.|  
|[COleControlSite::MoveWindow](#movewindow)|Изменение положения элемента управления узла.|  
|[COleControlSite::QuickActivate](#quickactivate)|Быстрое активирует размещенного элемента управления.|  
|[COleControlSite::SafeSetProperty](#safesetproperty)|Задает свойство или метод элемента управления без возможности создания исключения.|  
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Задает кнопку по умолчанию в окне.|  
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Получает идентификатор элемента управления.|  
|[COleControlSite::SetFocus](#setfocus)|Устанавливает фокус на узел элемента управления.|  
|[COleControlSite::SetProperty](#setproperty)|Задает указанное свойство размещенного элемента управления.|  
|[COleControlSite::SetPropertyV](#setpropertyv)|Задает указанное свойство размещенного элемента управления с переменный список аргументов.|  
|[COleControlSite::SetWindowPos](#setwindowpos)|Задает позицию элемента управления узла.|  
|[COleControlSite::SetWindowText](#setwindowtext)|Задает текст, размещенного элемента управления.|  
|[COleControlSite::ShowWindow](#showwindow)|Показывает или скрывает элемент управления узла.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Получает сведения о клавиатуры и мнемоник для размещенного элемента управления.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Определяет, является ли размещенный элемент управления элемента управления без окна.|  
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Содержит сведения на клавиатуре обработки для элемента управления.|  
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Файл cookie, точки подключения для элемента управления.|  
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Различные состояния для размещенного элемента управления.|  
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|`IPropertyNotifySink` Куки-файл элемента управления.|  
|[COleControlSite::m_dwStyle](#m_dwstyle)|Стили размещенного элемента управления.|  
|[COleControlSite::m_hWnd](#m_hwnd)|Дескриптор управления сайта.|  
|[COleControlSite::m_iidEvents](#m_iidevents)|Идентификатор интерфейса события для размещенного элемента управления.|  
|[COleControlSite::m_nID](#m_nid)|Идентификатор размещенного элемента управления.|  
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Указатель на `IOleInPlaceActiveObject` объект размещенного элемента управления.|  
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Контейнер размещенного элемента управления.|  
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|Указатель на `IOleInPlaceObject` объект размещенного элемента управления.|  
|[COleControlSite::m_pObject](#m_pobject)|Указатель на `IOleObjectInterface` интерфейса элемента управления.|  
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Указатель на `IOleInPlaceObjectWindowless` интерфейса элемента управления.|  
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Указатель на объект window для размещенного элемента управления.|  
|[COleControlSite::m_rect](#m_rect)|Аналитики сайта элемента управления.|  
  
## <a name="remarks"></a>Примечания  
 Эта поддержка является основным средством, с помощью которого внедренный элемент управления ActiveX получает сведения о расположении и узла, его моникер, его пользовательский интерфейс, его свойства окружения и других ресурсов, предоставляемых контейнером. `COleControlSite` полностью реализует [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502), [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706), [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), `IBoundObjectSite`, `INotifyDBEvents`, [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md) интерфейсов. Кроме того также реализуется интерфейс IDispatch (поддержки свойствам окружения и приемники событий).  
  
 Чтобы создать сайт элемента управления ActiveX с использованием `COleControlSite`, наследуйте класс от `COleControlSite`. В вашей `CWnd`-переопределения в производном классе для контейнера (например, в диалоговое окно) **CWnd::CreateControlSite** функции.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxocc.h  
  
##  <a name="binddefaultproperty"></a>  COleControlSite::BindDefaultProperty  
 Привязывает объект, вызывающий простое стандартное свойство привязки, отмеченное в библиотеке типов, базовый курсор, который определяется свойствами источника данных, имя пользователя, пароль и SQL элемента управления источником данных.  
  
```  
virtual void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Указывает **DISPID** свойства для элемента управления с привязкой к данным, который должен быть привязан к элементу управления источником данных.  
  
 *vtProp*  
 Указывает тип свойства для привязки, например, **VT_BSTR**, **VT_VARIANT**, и т. д.  
  
 *szFieldName*  
 Указывает имя столбца в курсоре, предоставляемые элементом управления источником данных, к которому будет привязано свойство.  
  
 *pDSCWnd*  
 Указатель на `CWnd`-производного объекта, на котором размещается элемент управления источника данных, к которому будет привязано свойство.  
  
### <a name="remarks"></a>Примечания  
 `CWnd` Объекта, на котором эта функция вызывается должен быть элементом управления с привязкой к данным.  
  
##  <a name="bindproperty"></a>  COleControlSite::BindProperty  
 Привязывает объект, вызывающий простой связанное свойство, отмеченное в библиотеке типов, базовый курсор, который определяется свойствами источника данных, имя пользователя, пароль и SQL элемента управления источником данных.  
  
```  
virtual void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispId*  
 Указывает **DISPID** свойства для элемента управления с привязкой к данным, который должен быть привязан к элементу управления источником данных.  
  
 *pWndDSC*  
 Указатель на `CWnd`-производного объекта, на котором размещается элемент управления источника данных, к которому будет привязано свойство.  
  
### <a name="remarks"></a>Примечания  
 `CWnd` Объекта, на котором эта функция вызывается должен быть элементом управления с привязкой к данным.  
  
##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite  
 Создает новое `COleControlSite` объекта.  
  
```  
explicit COleControlSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Параметры  
 *pCtrlCont*  
 Указатель контейнера элемента управления (который представляет окно, на котором размещается элемент управления AtiveX).  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) функции. Дополнительные сведения о настройке создания контейнеров см. в разделе [COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite).  
  
##  <a name="createcontrol"></a>  COleControlSite::CreateControl  
 Создает элемент управления ActiveX, размещаемую в `COleControlSite` объекта.  
  
```  
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);

 
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const POINT* ppt,  
    const SIZE* psize,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndCtrl*  
 Указатель на объект window, представляющий элемент управления.  
  
 *Идентификатор CLSID*  
 Класс уникальный идентификатор элемента управления.  
  
 *lpszWindowName*  
 Указатель на текст, отображаемый в элементе управления. Задает значение свойства winodw заголовок или текст (если таковые имеются).  
  
 *dwStyle*  
 Стили Windows. Доступные стили, которые будут отображаться в **примечания** раздела.  
  
 *Rect*  
 Задает размер и положение элемента управления. Это может быть либо `CRect` объекта или `RECT` структуры.  
  
 *nID*  
 Указывает идентификатор элемента управления дочернего окна.  
  
 *pPersist*  
 Указатель на `CFile` содержащий постоянное состояние для элемента управления. Значение по умолчанию — **NULL**, указывающее, что элемент управления инициализирует себя без восстановления свое состояние из любого из постоянного хранилища. В противном случае **NULL**, он должен быть указателем на `CFile`-производный объект, который содержит постоянных данных элемента управления в виде потока или хранилища. Удалось, эти данные были сохранены в предыдущей активации клиента. `CFile` Может содержать другие данные, но не устанавливается на первый байт постоянные данные во время вызова для чтения и записи указатель `CreateControl`.  
  
 *bStorage*  
 Указывает, является ли данные в *pPersist* должен интерпретироваться как `IStorage` или `IStream` данных. Если данные в *pPersist* — это хранилище *bStorage* должно быть **TRUE**. Если данные в *pPersist* представляет собой поток *bStorage* должно быть **FALSE**. Значение по умолчанию — **FALSE**.  
  
 *bstrLicKey*  
 Необязательные данные ключа лицензии. Эти данные требуется только для создания элементов управления, требующих ключ лицензии во время выполнения. Если элемент управления поддерживает лицензирования, необходимо указать лицензионный ключ для создания элемента управления для успешного выполнения. Значение по умолчанию — **NULL**.  
  
 *PPT*  
 Указатель на **ТОЧКИ** структуру, содержащую верхнего левого угла элемента управления. Размер элемента управления определяется по значению *psize*. *Ppt* и *psize* значения дополнительный способ задания размер и положение opf элемента управления.  
  
 *psize*  
 Указатель на **размер** структуру, содержащую размер элемента управления. Значение определяется верхнего левого угла *ppt*. *Ppt* и *psize* значения дополнительный способ задания размер и положение opf элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Только подмножество Windows *dwStyle* поддерживаемых флаги `CreateControl`:  
  
- **WS_VISIBLE** создает окно, которое изначально является видимым. Обязательно, если элемент управления видимым сразу же, как обычные окна.  
  
- **WS_DISABLED** создает окно, которое изначально отключены. Отключенного окна не может получать входные данные от пользователя. Можно задать, если элемент управления имеет свойство Enabled.  
  
- **WS_BORDER** создает окно с тонкой линии границы. Можно задать, если элемент управления имеет свойства BorderStyle.  
  
- **WS_GROUP** определяет первый элемент группы элементов управления. Пользователь может изменить фокус от одного элемента управления в группе к другому с помощью клавиш направления. Все элементы управления, имеющий **WS_GROUP** стиль после первого элемента управления принадлежать одной группе. Следующий элемент управления с **WS_GROUP** стиль завершает группу и запуске следующей группы.  
  
- **WS_TABSTOP** указывает элемент управления, который может получать фокус клавиатуры, когда пользователь нажимает клавишу TAB. Нажатие клавиши TAB изменяет фокус на следующий элемент управления из **WS_TABSTOP** стиля.  
  
 Создание элементов управления с размерами по умолчанию используйте вторую перегрузку.  
  
##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl  
 Уничтожает `COleControlSite` объекта.  
  
```  
virtual BOOL DestroyControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 После завершения объект освобождается из памяти и всех указателей на объект больше не являются допустимыми.  
  
##  <a name="doverb"></a>  COleControlSite::DoVerb  
 Выполняет указанную команду.  
  
```  
virtual HRESULT DoVerb(
    LONG nVerb,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *nVerb*  
 Указывает команду для выполнения. Он может включать одно из следующих:  
  
|Значение|Значение|Символ|  
|-----------|-------------|------------|  
|0|первичный глагол|`OLEIVERB_PRIMARY`|  
|-1|Команда получателя|(Нет)|  
|1|Отображает объект для редактирования.|`OLEIVERB_SHOW`|  
|-2|Изменяет элемент в отдельном окне.|`OLEIVERB_OPEN`|  
|-3|Скрывает объект.|`OLEIVERB_HIDE`|  
|-4|Активирует элемент управления на месте.|`OLEIVERB_UIACTIVATE`|  
|-5|Активирует элемент управления на месте, без дополнительных элементах пользовательского интерфейса.|`OLEIVERB_INPLACEACTIVATE`|  
|-7|Отобразить свойства элемента управления.|`OLEIVERB_PROPERTIES`|  
  
 *lpMsg*  
 Указатель на сообщение, вызвавшее его, чтобы активировать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается напрямую с помощью элемента управления `IOleObject` интерфейс для выполнения указанной команды. Если исключение создается в результате этого вызова функции `HRESULT` возвращен код ошибки.  
  
 Дополнительные сведения см. в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в Windows SDK.  
  
##  <a name="enabledsc"></a>  COleControlSite::EnableDSC  
 Включение данных источники для узла элемента управления.  
  
```  
virtual void EnableDSC();
```  
  
### <a name="remarks"></a>Примечания  
 Вызывается платформой для включения и инициализировать данные источники для узла элемента управления. Переопределите эту функцию, чтобы предоставить настраиваемое поведение.  
  
##  <a name="enablewindow"></a>  COleControlSite::EnableWindow  
 Включает или отключает мыши и клавиатуры для сайта элемента управления.  
  
```  
virtual BOOL EnableWindow(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 *bEnable*  
 Указывает, следует ли включить или отключить окно: **TRUE** Если включен, в противном случае входные данные окна **FALSE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно было отключено, иначе — 0.  
  
##  <a name="freezeevents"></a>  COleControlSite::FreezeEvents  
 Указывает, будет ли узел управления обработки или игнорирования события порождаемые из элемента управления.  
  
```  
void FreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Параметры  
 *bFreeze*  
 Указывает, требуется ли остановить прием событий для местоположения элемента управления. Ненулевое значение, если элемент управления не принимает события; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Если *bFreeze* — **TRUE**, сайт управления запросы управления для остановки fring события. Если *bFreeze* — **FALSE**, сайт управления запросы управления для продолжения вызова событий.  
  
> [!NOTE]
>  Элемент управления не является обязательным для остановки вызова событий, если запрошено сайта элемента управления. Он может продолжать активироваться, но все последующие события будут игнорироваться узлом элемента управления.  
  
##  <a name="getcontrolinfo"></a>  COleControlSite::GetControlInfo  
 Извлекает сведения о клавиши и сочетания поведение элемента управления.  
  
```  
void GetControlInfo();
```  
  
### <a name="remarks"></a>Примечания  
 Сведения хранятся в [COleControlSite::m_ctlInfo](#m_ctlinfo).  
  
##  <a name="getdefbtncode"></a>  COleControlSite::GetDefBtnCode  
 Определяет, является ли элемент управления является кнопкой по умолчанию.  
  
```  
DWORD GetDefBtnCode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Может принимать одно из следующих значений:  
  
- **DLGC_DEFPUSHBUTTON** элемент управления является кнопкой по умолчанию в диалоговом окне.  
  
- **DLGC_UNDEFPUSHBUTTON** управления не является кнопкой по умолчанию в диалоговом окне.  
  
- **0** элемент управления не кнопки.  
  
##  <a name="getdlgctrlid"></a>  COleControlSite::GetDlgCtrlID  
 Получает идентификатор элемента управления.  
  
```  
virtual int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор элемента диалогового окна элемента управления.  
  
##  <a name="geteventiid"></a>  COleControlSite::GetEventIID  
 Извлекает указатель на интерфейс событий для элемента управления по умолчанию.  
  
```  
BOOL GetEventIID(IID* piid);
```  
  
### <a name="parameters"></a>Параметры  
 *piid*  
 Указатель на идентификатор интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успеха, иначе — 0. В случае успешного выполнения *piid* содержит идентификатор интерфейса для интерфейса события элемента управления по умолчанию.  
  
##  <a name="getexstyle"></a>  COleControlSite::GetExStyle  
 Извлекает расширенные стили окна.  
  
```  
virtual DWORD GetExStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Окно управления расширенных стилей.  
  
### <a name="remarks"></a>Примечания  
 Чтобы получить регулярные стили, вызовите [COleControlSite::GetStyle](#getstyle).  
  
##  <a name="getproperty"></a>  COleControlSite::GetProperty  
 Возвращает свойства элемента управления, указанного в *dwDispID*.  
  
```  
virtual void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Указывает идентификатор диспетчера свойства, найденных на элемент управления по умолчанию `IDispatch` интерфейс, должны быть получены.  
  
 *vtProp*  
 Указывает тип свойства, которые требуется получить. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *pvProp*  
 Адрес переменной, которая получит значение свойства. Он должен соответствовать типу, определяемое *vtProp*.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение через *pvProp*.  
  
##  <a name="getstyle"></a>  COleControlSite::GetStyle  
 Извлекает стили элемента управления узла.  
  
```  
virtual DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стили окна.  
  
### <a name="remarks"></a>Примечания  
 Список возможных значений см. в разделе [стили Windows](../../mfc/reference/styles-used-by-mfc.md#window-styles). Чтобы получить расширенные стили управления сайта, вызовите [COleControlSite::GetExStyle](#getexstyle).  
  
##  <a name="getwindowtext"></a>  COleControlSite::GetWindowText  
 Получает текущий текст элемента управления.  
  
```  
virtual void GetWindowText(CString& str) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *str*  
 Ссылку на `CString` объект, содержащий текущий текст элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления поддерживает стандартное свойство заголовка, возвращается это значение. Если стандартное свойство заголовка не поддерживается, возвращается значение свойства Text.  
  
##  <a name="invokehelper"></a>  COleControlSite::InvokeHelper  
 Вызывает метод или свойство, указанное *dwDispID*, в контексте, определяемом *wFlags*.  
  
```  
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Указывает идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейс для вызова.  
  
 *wFlags*  
 Флаги, описывающие контекст вызова метода IDispatch::Invoke. Для возможности *wFlags* значения, в разделе `IDispatch::Invoke` в Windows SDK.  
  
 *vtRet*  
 Указывает тип возвращаемого значения. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *pvRet*  
 Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типу, определяемое *vtRet*.  
  
 *pbParamInfo*  
 Указатель на строку, завершающуюся значением null байтов, указывающих типы параметров после *pbParamInfo*. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Переменный список параметров типов, указанных в *pbParamInfo*.  
  
### <a name="remarks"></a>Примечания  
 *PbParamInfo* определяет типы параметров, передаваемых методу или свойству. Переменный список аргументов представлен... в объявлении синтаксиса.  
  
 Эта функция преобразует параметры в **VARIANTARG** значения, а затем вызывает `IDispatch::Invoke` метод в элементе управления. Если вызов `IDispatch::Invoke` завершается ошибкой, эта функция будет вызывать исключение. Если код состояния, возвращаемый `IDispatch::Invoke` — `DISP_E_EXCEPTION`, эта функция вызывает `COleDispatchException` объекта, в противном случае он вызывает `COleException`.  
  
##  <a name="invokehelperv"></a>  COleControlSite::InvokeHelperV  
 Вызывает метод или свойство, указанное *dwDispID*, в контексте, определяемом *wFlags*.  
  
```  
virtual void InvokeHelperV(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo,  
    va_list argList);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Указывает идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейс для вызова.  
  
 *wFlags*  
 Флаги, описывающие контекст вызова метода IDispatch::Invoke.  
  
 *vtRet*  
 Указывает тип возвращаемого значения. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *pvRet*  
 Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типу, определяемое *vtRet*.  
  
 *pbParamInfo*  
 Указатель на строку, завершающуюся значением null байтов, указывающих типы параметров после *pbParamInfo*. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *argList*  
 Указатель на список аргументов переменных.  
  
### <a name="remarks"></a>Примечания  
 *PbParamInfo* определяет типы параметров, передаваемых методу или свойству. Дополнительные параметры для метода или свойства, для которого вызван метод могут быть переданы с помощью *va_list* параметра.  
  
 Как правило, эта функция вызывается `COleControlSite::InvokeHelper`.  
  
##  <a name="isdefaultbutton"></a>  COleControlSite::IsDefaultButton  
 Определяет, является ли элемент управления кнопкой по умолчанию.  
  
```  
BOOL IsDefaultButton();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления кнопкой по умолчанию для окна, в противном случае — нуль.  
  
##  <a name="iswindowenabled"></a>  COleControlSite::IsWindowEnabled  
 Определяет, включен ли элемент управления узла.  
  
```  
virtual BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления включен, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Значение извлекается из стандартное свойство Enabled элемента управления.  
  
##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless  
 Определяет, является ли объект элемента управления без окна.  
  
```  
BOOL m_bIsWindowless;  
```  
  
### <a name="remarks"></a>Примечания  
 Ненулевое значение, если элемент управления не имеет окна, в противном случае — нуль.  
  
##  <a name="m_ctlinfo"></a>  COleControlSite::m_ctlInfo  
 Сведения об обработке ввода с клавиатуры элементом управления.  
  
```  
CONTROLINFO m_ctlInfo;  
```  
  
### <a name="remarks"></a>Примечания  
 Эти сведения хранятся в [CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734) структуры.  
  
##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink  
 Содержит точку подключения файла cookie из обработчика событий для элемента управления.  
  
```  
DWORD m_dwEventSink;  
```  
  
##  <a name="m_dwmiscstatus"></a>  COleControlSite::m_dwMiscStatus  
 Содержит различные сведения об элементе управления.  
  
```  
DWORD m_dwMiscStatus;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [OLEMISC, ПОЗВОЛЯЯ](http://msdn.microsoft.com/library/windows/desktop/ms678497)в Windows SDK.  
  
##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink  
 Содержит [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) куки-файл.  
  
```  
DWORD m_dwPropNotifySink;  
```  
  
##  <a name="m_dwstyle"></a>  COleControlSite::m_dwStyle  
 Содержит стили окна элемента управления.  
  
```  
DWORD m_dwStyle;  
```  
  
##  <a name="m_hwnd"></a>  COleControlSite::m_hWnd  
 Содержит `HWND` элемента управления, или **NULL** , если элемент управления без окон.  
  
```  
HWND m_hWnd;  
```  
  
##  <a name="m_iidevents"></a>  COleControlSite::m_iidEvents  
 Содержит идентификатор интерфейса интерфейс приемника событий для элемента управления по умолчанию.  
  
```  
IID m_iidEvents;  
```  
  
##  <a name="m_nid"></a>  COleControlSite::m_nID  
 Содержит идентификатор элемента управления диалогового окна элемента.  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_pactiveobject"></a>  COleControlSite::m_pActiveObject  
 Содержит [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) интерфейса элемента управления.  
  
```  
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;  
```  
  
##  <a name="m_pctrlcont"></a>  COleControlSite::m_pCtrlCont  
 Содержит контейнер элемента управления (представляющий формы).  
  
```  
COleControlContainer* m_pCtrlCont;  
```  
  
##  <a name="m_pinplaceobject"></a>  COleControlSite::m_pInPlaceObject  
 Содержит `IOleInPlaceObject` [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) интерфейса элемента управления.  
  
```  
LPOLEINPLACEOBJECT m_pInPlaceObject;  
```  
  
##  <a name="m_pobject"></a>  COleControlSite::m_pObject  
 Содержит **IOleObjectInterface** интерфейса элемента управления.  
  
```  
LPOLEOBJECT m_pObject;  
```  
  
##  <a name="m_pwindowlessobject"></a>  COleControlSite::m_pWindowlessObject  
 Содержит `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) интерфейса элемента управления.  
  
```  
IOleInPlaceObjectWindowless* m_pWindowlessObject;  
```  
  
##  <a name="m_pwndctrl"></a>  COleControlSite::m_pWndCtrl  
 Содержит указатель на `CWnd` объект, представляющий самого элемента управления.  
  
```  
CWnd* m_pWndCtrl;  
```  
  
##  <a name="m_rect"></a>  COleControlSite::m_rect  
 Содержит границы элемента управления относительно контейнера окна.  
  
```  
CRect m_rect;  
```  
  
##  <a name="modifystyle"></a>  COleControlSite::ModifyStyle  
 Изменение стилей элемента управления.  
  
```  
virtual BOOL ModifyStyle(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *dwRemove*  
 Стили, которые удалены из текущего стили окна.  
  
 *dwAdd*  
 Стили, чтобы добавить из текущего стили окна.  
  
 *nFlags*  
 Окно позиционирования флаги. Список возможных значений см. в разделе [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) функции в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если стили изменяются, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления stock свойство Enabled будет изменен для обеспечения соответствия параметр **WS_DISABLED**. Стандартное свойство стиль границы элемента управления будет изменен для обеспечения соответствия необходимых настроек для `WS_BORDER`. Все стили применяются непосредственно к дескриптор окна элемента управления, если он имеется.  
  
 Изменение стилей окна элемента управления. Стили, чтобы добавить или удалить можно комбинировать с помощью побитового или ( &#124; ) оператор. В разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) функции в Windows SDK для информации о стилях доступном периоде.  
  
 Если *nFlags* отлично от нуля, `ModifyStyle` вызывает функцию Win32 `SetWindowPos`и на экран окно путем объединения *nFlags* с использованием следующих четырех флагов:  
  
- `SWP_NOSIZE` Сохраняет текущий размер.  
  
- `SWP_NOMOVE` Сохраняет текущую позицию.  
  
- `SWP_NOZORDER` Сохраняет текущего Z-порядка.  
  
- `SWP_NOACTIVATE` Не активирует окно.  
  
 Для изменения окна расширенных стилей, вызовите метод [ModifyStyleEx](#modifystyleex).  
  
##  <a name="modifystyleex"></a>  COleControlSite::ModifyStyleEx  
 Изменяет расширенные стили элемента управления.  
  
```  
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *dwRemove*  
 Расширенные стили, который необходимо удалить из текущей стили окна.  
  
 *dwAdd*  
 Расширенные стили для добавления из текущего стили окна.  
  
 *nFlags*  
 Окно позиционирования флаги. Список возможных значений см. в разделе [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) функции в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если стили изменяются, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Стандартное свойство внешнего вида элемента управления будет изменен для обеспечения соответствия параметр **WS_EX_CLIENTEDGE**. Все другие расширенные стили окна применяются непосредственно к дескриптор окна элемента управления, если он имеется.  
  
 Изменяет окна расширенные стили объекта сайта элемента управления. Стили, чтобы добавить или удалить можно комбинировать с помощью побитового или ( &#124; ) оператор. В разделе [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) функции в Windows SDK для информации о стилях доступном периоде.  
  
 Если *nFlags* отлично от нуля, `ModifyStyleEx` вызывает функцию Win32 `SetWindowPos`и на экран окно путем объединения *nFlags* с использованием следующих четырех флагов:  
  
- `SWP_NOSIZE` Сохраняет текущий размер.  
  
- `SWP_NOMOVE` Сохраняет текущую позицию.  
  
- `SWP_NOZORDER` Сохраняет текущего Z-порядка.  
  
- `SWP_NOACTIVATE` Не активирует окно.  
  
 Для изменения окна расширенных стилей, вызовите метод [ModifyStyle](#modifystyle).  
  
##  <a name="movewindow"></a>  COleControlSite::MoveWindow  
 Изменение положения элемента управления.  
  
```  
virtual void MoveWindow(
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Новая позиция в левой части окна.  
  
 *y*  
 Новое положение верхнего края окна.  
  
 *nWidth*  
 Новая ширина окна  
  
 *nHeight*  
 Новая высота окна.  
  
##  <a name="quickactivate"></a>  COleControlSite::QuickActivate  
 Быстрое активирует элемента управления в контейнере.  
  
```  
virtual BOOL QuickActivate();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если узел элемента управления был активирован, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Эта функция должна вызываться только в том случае, если пользователь переопределяет процесс создания элемента управления.  
  
 `IPersist*::Load` И `IPersist*::InitNew` методов следует вызывать после выполнения быстрого активации. Элемент управления должны устанавливать соединения с помощью приемники контейнера во время быстрой активации. Тем не менее, эти соединения не являются динамическими до `IPersist*::Load` или `IPersist*::InitNew` был вызван.  
  
##  <a name="safesetproperty"></a>  COleControlSite::SafeSetProperty  
 Задает свойства элемента управления, указанного в *dwDispID*.  
  
```  
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Указывает идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейса, которому присваивается.  
  
 *vtProp*  
 Указывает тип должно быть задано свойство. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Один параметр типа, заданного параметром *vtProp*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  В отличие от `SetProperty` и `SetPropertyV`, если возникает ошибка (например, при попытке задать свойство несуществующего), исключение не возникает.  
  
##  <a name="setdefaultbutton"></a>  COleControlSite::SetDefaultButton  
 Задает элемент управления кнопкой по умолчанию.  
  
```  
void SetDefaultButton(BOOL bDefault);
```  
  
### <a name="parameters"></a>Параметры  
 *bПо умолчанию*  
 Ненулевое значение, если элемент управления должен стать кнопки по умолчанию. в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Элемент управления должен иметь **OLEMISC_ACTSLIKEBUTTON** состояние бит.  
  
##  <a name="setdlgctrlid"></a>  COleControlSite::SetDlgCtrlID  
 Изменяет значение идентификатора элемента управления диалогового окна.  
  
```  
virtual int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Новое значение идентификатора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения предыдущего диалога элемента идентификатор окна. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setfocus"></a>  COleControlSite::SetFocus  
 Устанавливает фокус на элемент управления.  
  
```  
virtual CWnd* SetFocus();  
virtual CWnd* SetFocus(LPMSG lpmsg);
```  
  
### <a name="parameters"></a>Параметры  
 *lpmsg*  
 Указатель на [структура MSG](../../mfc/reference/msg-structure1.md). Эта структура содержит сообщения Windows вызывающей срабатывание триггера `SetFocus` запрос для элемента управления, содержащихся в текущем узле элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно, ранее имевший фокус.  
  
##  <a name="setproperty"></a>  COleControlSite::SetProperty  
 Задает свойства элемента управления, указанного в *dwDispID*.  
  
```  
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Указывает идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейса, которому присваивается.  
  
 *vtProp*  
 Указывает тип должно быть задано свойство. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Один параметр типа, заданного параметром *vtProp*.  
  
### <a name="remarks"></a>Примечания  
 Если `SetProperty` возникает ошибка, создается исключение.  
  
 Тип исключения определяется значение, возвращаемое попытка установить свойства или метода. Если возвращается значение `DISP_E_EXCEPTION`, `COleDispatchExcpetion` вызываться исключение; в противном случае `COleException`.  
  
##  <a name="setpropertyv"></a>  COleControlSite::SetPropertyV  
 Задает свойства элемента управления, указанного в *dwDispID*.  
  
```  
virtual void SetPropertyV(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    va_list argList);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Указывает идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейса, которому присваивается.  
  
 *vtProp*  
 Указывает тип должно быть задано свойство. Возможные значения см. в разделе «Примечания» [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *argList*  
 Указатель на список аргументов.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные параметры для метода или свойства, для которого вызван метод может быть passeed с помощью *arg_list* параметра. Если `SetProperty` возникает ошибка, создается исключение.  
  
 Тип исключения определяется значение, возвращаемое попытка установить свойства или метода. Если возвращается значение `DISP_E_EXCEPTION`, `COleDispatchExcpetion` вызываться исключение; в противном случае `COleException`.  
  
##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos  
 Задает размер, положение и Z-порядку сайта элемента управления.  
  
```  
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Параметры  
 *pWndInsertAfter*  
 Указатель на окно.  
  
 *x*  
 Новая позиция в левой части окна.  
  
 *y*  
 Новое положение верхнего края окна.  
  
 *CX*  
 Новая ширина окна  
  
 *CY*  
 Новая высота окна.  
  
 *nFlags*  
 Задает окно изменения размеров и положения флаги. Возможные значения см. в разделе «Примечания» [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
##  <a name="setwindowtext"></a>  COleControlSite::SetWindowText  
 Задает текст для узла элемента управления.  
  
```  
virtual void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszString*  
 Указатель на строку, завершающуюся значением null для использования в качестве нового текста заголовка или элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция сначала пытается задать стандартное свойство заголовка. Если стандартное свойство заголовка не поддерживается, вместо этого устанавливается свойство Text.  
  
##  <a name="showwindow"></a>  COleControlSite::ShowWindow  
 Задает состояние отображения окна.  
  
```  
virtual BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>Параметры  
 *nCmdShow*  
 Указывает, как будет отображаться узел элемента управления. Он должен быть одним из следующих значений:  
  
- **SW_HIDE** скрывает это окно и передает активации в другом окне.  
  
- **SW_MINIMIZE** сворачивает окно и активирует окно верхнего уровня в списке в системе.  
  
- **SW_RESTORE** активация и отображение окна. Если окно сворачивать или разворачивать, Windows восстанавливает его исходный размер и положение.  
  
- **SW_SHOW** активирует окно и отображает его в его текущего размера и положения.  
  
- **SW_SHOWMAXIMIZED** активирует окно и отображает его в виде развернутого окна.  
  
- **SW_SHOWMINIMIZED** активирует окно и отображает его в виде значка.  
  
- **SW_SHOWMINNOACTIVE** свернуть окно в виде значка. Окно, которое в данный момент активна остается активным.  
  
- **SW_SHOWNA** отображает окно в ее текущем состоянии. Окно, которое в данный момент активна остается активным.  
  
- **SW_SHOWNOACTIVATE** отображает окно в свои последние размер и положение. Окно, которое в данный момент активна остается активным.  
  
- **SW_SHOWNORMAL** активация и отображение окна. Если окно сворачивать или разворачивать, Windows восстанавливает его исходный размер и положение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно было ранее видимым. 0, если окно ранее было скрыто.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)
