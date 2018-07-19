---
title: Класс COleControlSite | Документация Майкрософт
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
ms.openlocfilehash: 5c6f84f575edbcaf8ecc64f424f3225d969d6a7f
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850359"
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
|[COleControlSite::CreateControl](#createcontrol)|Создает размещаемого элемента управления ActiveX.|  
|[COleControlSite::DestroyControl](#destroycontrol)|Уничтожает размещенного элемента управления.|  
|[COleControlSite::DoVerb](#doverb)|Выполняет определенные команды размещенного элемента управления.|  
|[COleControlSite::EnableDSC](#enabledsc)|Включает подключения для сайта управления источников данных.|  
|[COleControlSite::EnableWindow](#enablewindow)|Позволяет веб-элемента управления узла.|  
|[COleControlSite::FreezeEvents](#freezeevents)|Указывает, если узел управления принимает события.|  
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|Получает код кнопки по умолчанию для размещенного элемента управления.|  
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|Извлекает идентификатор элемента управления.|  
|[COleControlSite::GetEventIID](#geteventiid)|Извлекает идентификатор интерфейс событий для размещаемого элемента управления.|  
|[COleControlSite::GetExStyle](#getexstyle)|Извлекает расширенные стили элемента управления узла.|  
|[COleControlSite::GetProperty](#getproperty)|Извлекает указанное свойство размещенного элемента управления.|  
|[COleControlSite::GetStyle](#getstyle)|Получает стили элемента управления узла.|  
|[COleControlSite::GetWindowText](#getwindowtext)|Извлекает текст размещенного элемента управления.|  
|[COleControlSite::InvokeHelper](#invokehelper)|Вызова определенного метода размещенного элемента управления.|  
|[COleControlSite::InvokeHelperV](#invokehelperv)|Вызова определенного метода размещенного элемента управления с переменный список аргументов.|  
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|Определяет, является ли элемент управления кнопкой по умолчанию в окне.|  
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|Проверяет режим отображения элемента управления узла.|  
|[COleControlSite::ModifyStyle](#modifystyle)|Изменяет текущий расширенные стили элемента управления узла.|  
|[COleControlSite::ModifyStyleEx](#modifystyleex)|Изменяет текущий стили элемента управления узла.|  
|[COleControlSite::MoveWindow](#movewindow)|Изменяет позицию узла элемента управления.|  
|[COleControlSite::QuickActivate](#quickactivate)|Быстрое активирует размещенного элемента управления.|  
|[COleControlSite::SafeSetProperty](#safesetproperty)|Задает свойство или метод элемента управления без вероятность возникновения исключения.|  
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|Задает кнопку по умолчанию в окне.|  
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|Извлекает идентификатор элемента управления.|  
|[COleControlSite::SetFocus](#setfocus)|Устанавливает фокус на сайт элемента управления.|  
|[COleControlSite::SetProperty](#setproperty)|Задает указанное свойство класса размещенного элемента управления.|  
|[COleControlSite::SetPropertyV](#setpropertyv)|Задает указанное свойство класса размещенного элемента управления с переменный список аргументов.|  
|[COleControlSite::SetWindowPos](#setwindowpos)|Задает положение элемента управления узла.|  
|[COleControlSite::SetWindowText](#setwindowtext)|Задает текст, размещаемого элемента управления.|  
|[COleControlSite::ShowWindow](#showwindow)|Показывает или скрывает элемент управления сайта.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](#getcontrolinfo)|Извлекает сведения клавиатуры и назначенные клавиши для размещаемого элемента управления.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|Определяет, является ли размещенный элемент управления элемента управления без окна.|  
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|Содержит сведения о для элемента управления для обработки событий клавиатуры.|  
|[COleControlSite::m_dwEventSink](#m_dweventsink)|Файл cookie точка подключения элемента управления.|  
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|Различные состояния для размещаемого элемента управления.|  
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|`IPropertyNotifySink` Куки-файл элемента управления.|  
|[COleControlSite::m_dwStyle](#m_dwstyle)|Стили размещенного элемента управления.|  
|[COleControlSite::m_hWnd](#m_hwnd)|Дескриптор элемента управления узла.|  
|[COleControlSite::m_iidEvents](#m_iidevents)|Идентификатор интерфейса событий для размещаемого элемента управления.|  
|[COleControlSite::m_nID](#m_nid)|Идентификатор размещаемого элемента управления.|  
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|Указатель на `IOleInPlaceActiveObject` объект размещенного элемента управления.|  
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|Контейнер размещаемого элемента управления.|  
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|Указатель на `IOleInPlaceObject` объект размещенного элемента управления.|  
|[COleControlSite::m_pObject](#m_pobject)|Указатель на `IOleObjectInterface` интерфейса элемента управления.|  
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|Указатель на `IOleInPlaceObjectWindowless` интерфейса элемента управления.|  
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|Указатель на объект окна для размещаемого элемента управления.|  
|[COleControlSite::m_rect](#m_rect)|Размеры элемента управления узла.|  
  
## <a name="remarks"></a>Примечания  
 Эта поддержка является основным средством, по которому внедренный элемент управления ActiveX получает информацию о местонахождении и экстент его сайта отображения, его моникер, его пользовательский интерфейс, его внешние свойства и другие ресурсы, предоставленных его контейнером. `COleControlSite` полностью реализует [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502), [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706), [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), `IBoundObjectSite`, `INotifyDBEvents`, [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md) интерфейсов. Кроме того также реализован интерфейс IDispatch (поддержки свойства окружающей среды и приемники событий).  
  
 Чтобы создать сайт элемента управления ActiveX с помощью `COleControlSite`, являются производными от класса `COleControlSite`. В вашей `CWnd`-переопределения в производном классе для контейнера (например, диалогового окна) `CWnd::CreateControlSite` функции.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxocc.h  
  
##  <a name="binddefaultproperty"></a>  COleControlSite::BindDefaultProperty  
 Привязывает объект, вызывающий простое стандартное свойство привязки, отмеченное в библиотеке типов, на базовый курсор, который определяется свойствами DataSource, имя пользователя, пароль и SQL элемента управления источника данных.  
  
```  
virtual void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Указывает идентификатор DISPID свойства для элемента управления с привязкой данных, который должен быть привязан к элементу управления источника данных.  
  
 *vtProp*  
 Указывает тип свойства для привязки, например, VT_BSTR VT_VARIANT и т. д.  
  
 *szFieldName*  
 Указывает имя столбца в курсоре, предоставляемые элементом управления источника данных, к которому будет привязано свойство.  
  
 *pDSCWnd*  
 Указатель на `CWnd`-производного объекта, на котором размещается элемент управления источника данных, к которому будет привязано свойство.  
  
### <a name="remarks"></a>Примечания  
 `CWnd` Объекта, на котором вы вызываете эту функцию должен быть элементом управления с привязкой к данным.  
  
##  <a name="bindproperty"></a>  COleControlSite::BindProperty  
 Привязывает объект, вызывающий простой привязанное свойство, отмеченное в библиотеке типов на базовый курсор, который определяется свойствами DataSource, имя пользователя, пароль и SQL элемента управления источника данных.  
  
```  
virtual void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispId*  
 Указывает идентификатор DISPID свойства для элемента управления с привязкой данных, который должен быть привязан к элементу управления источника данных.  
  
 *pWndDSC*  
 Указатель на `CWnd`-производного объекта, на котором размещается элемент управления источника данных, к которому будет привязано свойство.  
  
### <a name="remarks"></a>Примечания  
 `CWnd` Объекта, на котором вы вызываете эту функцию должен быть элементом управления с привязкой к данным.  
  
##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite  
 Создает новый `COleControlSite` объекта.  
  
```  
explicit COleControlSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>Параметры  
 *pCtrlCont*  
 Указатель на контейнера элемента управления (который представляет окно, в которой размещен элемент управления AtiveX).  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) функции. Дополнительные сведения о настройке создание контейнеров см. в разделе [COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite).  
  
##  <a name="createcontrol"></a>  COleControlSite::CreateControl  
 Создает элемент управления ActiveX, проводимых `COleControlSite` объекта.  
  
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
  
 *CLSID*  
 Класс уникальный идентификатор элемента управления.  
  
 *lpszWindowName*  
 Указатель на текст, отображаемый в элементе управления. Задает значение свойства winodw заголовок или текст (если таковые имеются).  
  
 *dwStyle*  
 Стили Windows. Доступные стили отображаются в категории **"Примечания"** раздел.  
  
 *Rect*  
 Задает размер и положение элемента управления. Может быть либо `CRect` объекта или `RECT` структуры.  
  
 *nID*  
 Указывает идентификатор элемента управления дочернего окна.  
  
 *pPersist*  
 Указатель на `CFile` содержащий сохраняемого состояния для элемента управления. Значение по умолчанию — NULL, указывающее, что элемент управления инициализирует себя без восстановления состояния из любой постоянного хранилища. Если значение не NULL, он должен быть указателем для `CFile`-производного объекта, который содержит постоянных данных элемента управления в форме потока или хранилища. Может, эти данные были сохранены в предыдущей активации клиента. `CFile` Может содержать другие данные, но должен иметь свой указатель чтения и записи, задайте до получения первого байта из постоянных данных во время вызова `CreateControl`.  
  
 *bStorage*  
 Указывает, является ли данные в *pPersist* следует интерпретировать как `IStorage` или `IStream` данных. Если данные в *pPersist* в качестве хранилища, *bStorage* необходимо указать значение TRUE. Если данные в *pPersist* представляет собой поток *bStorage* должен иметь значение FALSE. Значение по умолчанию — FALSE.  
  
 *bstrLicKey*  
 Необязательные данные ключа лицензии. Эти данные требуется только для создания элементов управления, требующих выполнения лицензионного ключа. Если элемент управления поддерживает лицензирования, необходимо предоставить ключ лицензии для создания элемента управления для успешного выполнения. Значение по умолчанию имеет значение NULL.  
  
 *PPT*  
 Указатель на `POINT` структуру, содержащую верхнего левого угла элемента управления. Размер элемента управления определяется по значению *psize*. *Ppt* и *psize* значения необязательного метода указания размера и размещения opf элемента управления.  
  
 *psize*  
 Указатель на `SIZE` структуру, содержащую размер элемента управления. Верхнего левого угла определяется по значению *ppt*. *Ppt* и *psize* значения необязательного метода указания размера и размещения opf элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Только подмножество Windows *dwStyle* флаги поддерживаются `CreateControl`:  
  
- WS_VISIBLE создает окно, которое изначально является видимым. Обязательно, если элемент управления должен отображаться сразу же, как обычные окна.  
  
- WS_DISABLED создает окно, которое изначально было отключено. Отключенного окна не может принимать входные данные от пользователя. Можно задать, если элемент управления имеет свойство Enabled.  
  
- WS_BORDER создает окно с тонкой линии границы. Можно задать, если элемент управления имеет свойства BorderStyle.  
  
- WS_GROUP задает группу элементов управления к первому элементу управления. Пользователь может изменить фокус от одного элемента управления в группе к другому с использованием ключей, направление. Все элементы управления, определенные с помощью стиля WS_GROUP после первого элемента управления, которым принадлежат той же группе. Следующий элемент управления с помощью стиля WS_GROUP завершает группе и запускается следующая команда.  
  
- WS_TABSTOP указывает элемент управления, который может получать фокус клавиатуры, когда пользователь нажимает клавишу TAB. Нажатие клавиши TAB изменяет фокус клавиатуры WS_TABSTOP стиля к следующему элементу управления.  
  
 Используйте вторую перегрузку для создания элементов управления с размером по умолчанию.  
  
##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl  
 Уничтожает `COleControlSite` объекта.  
  
```  
virtual BOOL DestroyControl();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 После завершения объект освобождается из памяти и все указатели на объект больше не действительны.  
  
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
|0|первичный глагол|OLEIVERB_PRIMARY|  
|-1|Вторичный команды|(Нет)|  
|1|Отображает объект для редактирования.|OLEIVERB_SHOW|  
|-2|Изменяет элемент в отдельном окне.|OLEIVERB_OPEN|  
|-3|Скрывает объект.|OLEIVERB_HIDE|  
|-4|Активирует элемент управления на месте.|OLEIVERB_UIACTIVATE|  
|-5|Активирует элемент управления на месте, без дополнительных элементах пользовательского интерфейса.|OLEIVERB_INPLACEACTIVATE|  
|-7|Отображение свойств элемента управления.|OLEIVERB_PROPERTIES|  
  
 *lpMsg*  
 Указатель на сообщение, вызвавшее активацию элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывает непосредственно через свойство элемента управления `IOleObject` интерфейс для выполнения указанной команды. Если исключение возникает в результате этого вызова функции, возвращается код ошибки HRESULT.  
  
 Дополнительные сведения см. в разделе [функция IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) в пакете Windows SDK.  
  
##  <a name="enabledsc"></a>  COleControlSite::EnableDSC  
 Включает подключения для сайта управления источников данных.  
  
```  
virtual void EnableDSC();
```  
  
### <a name="remarks"></a>Примечания  
 Вызывается платформой для включения и инициализировать данные, источники для узла элемента управления. Переопределите эту функцию, чтобы предоставить настраиваемое поведение.  
  
##  <a name="enablewindow"></a>  COleControlSite::EnableWindow  
 Включает или отключает мыши и клавиатуры для сайта элемента управления.  
  
```  
virtual BOOL EnableWindow(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 *bEnable*  
 Указывает, следует ли включить или отключить окно: значение TRUE, если окно ввода включена, в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно было отключено, иначе — 0.  
  
##  <a name="freezeevents"></a>  COleControlSite::FreezeEvents  
 Указывает, будет ли узел управления обработки или игнорирования события, инициируемые из элемента управления.  
  
```  
void FreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Параметры  
 *bFreeze*  
 Указывает, требуется ли остановить прием событий для местоположения элемента управления. Ненулевое значение, если элемент управления не принимает события; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Если *bFreeze* имеет значение TRUE, элемент управления для остановки событий перенесите запрашивает сайт элемента управления. Если *bFreeze* имеет значение FALSE, сайт управления запросы по-прежнему генерирует события элемента управления.  
  
> [!NOTE]
>  Элемент управления не является обязательным для остановки вызова событий при запросе веб-узел элемента управления. Он может продолжать активироваться, но все последующие события будут игнорироваться подсистемой управления сайта.  
  
##  <a name="getcontrolinfo"></a>  COleControlSite::GetControlInfo  
 Извлекает сведения о назначенных клавиш клавиатуры и клавиатуры поведение элемента управления.  
  
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
  
- DLGC_DEFPUSHBUTTON управления является кнопкой по умолчанию в диалоговом окне.  
  
- Элемент управления DLGC_UNDEFPUSHBUTTON не является кнопкой по умолчанию в диалоговом окне.  
  
- **0** управления не является кнопкой.  
  
##  <a name="getdlgctrlid"></a>  COleControlSite::GetDlgCtrlID  
 Извлекает идентификатор элемента управления.  
  
```  
virtual int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор элемента диалогового окна элемента управления.  
  
##  <a name="geteventiid"></a>  COleControlSite::GetEventIID  
 Извлекает указатель на интерфейс событий элемента управления по умолчанию.  
  
```  
BOOL GetEventIID(IID* piid);
```  
  
### <a name="parameters"></a>Параметры  
 *piid*  
 Указатель на идентификатор интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно, иначе — 0. В случае успешного выполнения *piid* содержит идентификатор интерфейса для интерфейса события элемента управления по умолчанию.  
  
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
 Возвращает свойства элемента управления, определяемое *dwDispID*.  
  
```  
virtual void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Определяет идентификатор диспетчера свойства, найденных на элемента управления по умолчанию `IDispatch` интерфейс, должны быть получены.  
  
 *vtProp*  
 Тип извлекаемого свойства. Возможные значения см. в разделе "Примечания" для [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *pvProp*  
 Адрес переменной, которая будет принимать значение свойства. Он должен соответствовать типа, заданного параметром *vtProp*.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию возвращается через *pvProp*.  
  
##  <a name="getstyle"></a>  COleControlSite::GetStyle  
 Получает стили элемента управления узла.  
  
```  
virtual DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стили окна.  
  
### <a name="remarks"></a>Примечания  
 Список возможных значений см. в разделе [стили Windows](../../mfc/reference/styles-used-by-mfc.md#window-styles). Чтобы получить расширенные стили узла управления, вызовите [COleControlSite::GetExStyle](#getexstyle).  
  
##  <a name="getwindowtext"></a>  COleControlSite::GetWindowText  
 Извлекает текущий текст элемента управления.  
  
```  
virtual void GetWindowText(CString& str) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *str*  
 Ссылку на `CString` объект, содержащий текущий текст элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Если элемент управления поддерживает свойство Caption акций, возвращается это значение. Если свойство Caption акций не поддерживается, возвращается значение для свойства Text.  
  
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
 Определяет идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейс для вызова.  
  
 *wFlags*  
 Флаги, описывающие контекст вызова метода IDispatch::Invoke. Для возможности *wFlags* значения, см. в разделе `IDispatch::Invoke` в пакете Windows SDK.  
  
 *vtRet*  
 Указывает тип возвращаемого значения. Возможные значения см. в разделе "Примечания" для [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *pvRet*  
 Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типа, заданного параметром *vtRet*.  
  
 *pbParamInfo*  
 Указатель на заканчивающуюся нулем строку байтов, определяющую типы параметров после *pbParamInfo*. Возможные значения см. в разделе "Примечания" для [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Переменный список параметров, типов, указанных в *pbParamInfo*.  
  
### <a name="remarks"></a>Примечания  
 *PbParamInfo* параметр указывает типы параметров, передаваемых в метод или свойство. Переменный список аргументов представлен... в объявлении синтаксиса.  
  
 Эта функция преобразует параметры в значения VARIANTARG, а затем вызывает `IDispatch::Invoke` метод в элементе управления. Если вызов `IDispatch::Invoke` завершается ошибкой, эта функция будет создано исключение. Если код состояния, возвращаемый `IDispatch::Invoke` — `DISP_E_EXCEPTION`, эта функция создает `COleDispatchException` объекта, в противном случае он вызывает `COleException`.  
  
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
 Определяет идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейс для вызова.  
  
 *wFlags*  
 Флаги, описывающие контекст вызова метода IDispatch::Invoke.  
  
 *vtRet*  
 Указывает тип возвращаемого значения. Возможные значения см. в разделе "Примечания" для [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *pvRet*  
 Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типа, заданного параметром *vtRet*.  
  
 *pbParamInfo*  
 Указатель на заканчивающуюся нулем строку байтов, определяющую типы параметров после *pbParamInfo*. Возможные значения см. в разделе "Примечания" для [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *argList*  
 Указатель на список аргументов переменных.  
  
### <a name="remarks"></a>Примечания  
 *PbParamInfo* параметр указывает типы параметров, передаваемых в метод или свойство. Дополнительные параметры для метода или свойства вызываемого могут быть переданы с помощью *va_list* параметра.  
  
 Как правило, эта функция вызывается `COleControlSite::InvokeHelper`.  
  
##  <a name="isdefaultbutton"></a>  COleControlSite::IsDefaultButton  
 Определяет, если элемент управления является кнопкой по умолчанию.  
  
```  
BOOL IsDefaultButton();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления является кнопкой по умолчанию в окне противном случае — нуль.  
  
##  <a name="iswindowenabled"></a>  COleControlSite::IsWindowEnabled  
 Определяет, включена ли сайт элемента управления.  
  
```  
virtual BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления включен; в противном случае — ноль.  
  
### <a name="remarks"></a>Примечания  
 Значение извлекается из стандартное свойство Enabled элемента управления.  
  
##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless  
 Определяет, если объект является безоконного управления.  
  
```  
BOOL m_bIsWindowless;  
```  
  
### <a name="remarks"></a>Примечания  
 Ненулевое значение, если элемент управления не имеет окна, в противном случае — ноль.  
  
##  <a name="m_ctlinfo"></a>  COleControlSite::m_ctlInfo  
 Сведения о том, как ввод с клавиатуры обрабатывается элементом управления.  
  
```  
CONTROLINFO m_ctlInfo;  
```  
  
### <a name="remarks"></a>Примечания  
 Эти сведения хранятся в [CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734) структуры.  
  
##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink  
 Содержит файл cookie точку подключения из приемника событий элемента управления.  
  
```  
DWORD m_dwEventSink;  
```  
  
##  <a name="m_dwmiscstatus"></a>  COleControlSite::m_dwMiscStatus  
 Содержит различные сведения об элементе управления.  
  
```  
DWORD m_dwMiscStatus;  
```  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497)в пакете Windows SDK.  
  
##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink  
 Содержит [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) файла cookie.  
  
```  
DWORD m_dwPropNotifySink;  
```  
  
##  <a name="m_dwstyle"></a>  COleControlSite::m_dwStyle  
 Содержит стили окна элемента управления.  
  
```  
DWORD m_dwStyle;  
```  
  
##  <a name="m_hwnd"></a>  COleControlSite::m_hWnd  
 Содержит дескриптор HWND элемента управления, или значение NULL, если элемент управления без окон.  
  
```  
HWND m_hWnd;  
```  
  
##  <a name="m_iidevents"></a>  COleControlSite::m_iidEvents  
 Содержит идентификатор интерфейса приемника событий для элемента управления по умолчанию.  
  
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
 Содержит контейнера элемента управления (представляющие форме).  
  
```  
COleControlContainer* m_pCtrlCont;  
```  
  
##  <a name="m_pinplaceobject"></a>  COleControlSite::m_pInPlaceObject  
 Содержит `IOleInPlaceObject` [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) интерфейса элемента управления.  
  
```  
LPOLEINPLACEOBJECT m_pInPlaceObject;  
```  
  
##  <a name="m_pobject"></a>  COleControlSite::m_pObject  
 Содержит `IOleObjectInterface` интерфейса элемента управления.  
  
```  
LPOLEOBJECT m_pObject;  
```  
  
##  <a name="m_pwindowlessobject"></a>  COleControlSite::m_pWindowlessObject  
 Содержит `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) интерфейса элемента управления.  
  
```  
IOleInPlaceObjectWindowless* m_pWindowlessObject;  
```  
  
##  <a name="m_pwndctrl"></a>  COleControlSite::m_pWndCtrl  
 Содержит указатель на `CWnd` объект, представляющий сам элемент управления.  
  
```  
CWnd* m_pWndCtrl;  
```  
  
##  <a name="m_rect"></a>  COleControlSite::m_rect  
 Содержит границы элемента управления, относительно окна контейнера.  
  
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
 Стили, который необходимо удалить из текущей стили окна.  
  
 *dwAdd*  
 Стили, которые добавлены из текущего стили окна.  
  
 *nFlags*  
 Окно позиционирования флаги. Список возможных значений см. в разделе [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) функции в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если стили изменяются, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления stock свойство Enabled будут изменены в соответствии с параметром для WS_DISABLED. Стандартное свойство стиль границы элемента управления будет изменен в соответствии с необходимых настроек для WS_BORDER. Все другие стили применяются непосредственно к дескриптор окна элемента управления, если таковой имеется.  
  
 Изменение стилей окна элемента управления. Стили, чтобы добавить или удалить могут объединяться с помощью побитовой операции или ( &#124; ) оператор. См. в разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) функции в пакете SDK для Windows, сведения о стилях доступное окно.  
  
 Если *nFlags* не равно нулю, `ModifyStyle` вызывает функцию Win32 `SetWindowPos`и перерисовывает окна путем объединения *nFlags* с использованием следующих четырех флагов:  
  
- SWP_NOSIZE сохраняет текущий размер.  
  
- SWP_NOMOVE сохраняет текущую позицию.  
  
- SWP_NOZORDER сохраняет текущий Z-порядка.  
  
- SWP_NOACTIVATE не активирует окно.  
  
 Для изменения окна расширенных стилей, вызовите [ModifyStyleEx](#modifystyleex).  
  
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
 Расширенные стили нужно добавить стили текущего окна.  
  
 *nFlags*  
 Окно позиционирования флаги. Список возможных значений см. в разделе [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) функции в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если стили изменяются, в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Биржевая элемента управления свойства внешнего вида будут изменены в соответствии с параметром для WS_EX_CLIENTEDGE. Все другие расширенные стили окна применяются непосредственно к дескриптор окна элемента управления, если таковой имеется.  
  
 Изменяет расширенные стили объекта сайта элемента управления окна. Стили, чтобы добавить или удалить могут объединяться с помощью побитовой операции или ( &#124; ) оператор. См. в разделе [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) функции в пакете SDK для Windows, сведения о стилях доступное окно.  
  
 Если *nFlags* не равно нулю, `ModifyStyleEx` вызывает функцию Win32 `SetWindowPos`и перерисовывает окна путем объединения *nFlags* с использованием следующих четырех флагов:  
  
- SWP_NOSIZE сохраняет текущий размер.  
  
- SWP_NOMOVE сохраняет текущую позицию.  
  
- SWP_NOZORDER сохраняет текущий Z-порядка.  
  
- SWP_NOACTIVATE не активирует окно.  
  
 Для изменения окна расширенных стилей, вызовите [ModifyStyle](#modifystyle).  
  
##  <a name="movewindow"></a>  COleControlSite::MoveWindow  
 Изменяет положение элемента управления.  
  
```  
virtual void MoveWindow(
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Новое положение левой части окна.  
  
 *y*  
 Новое положение верхней части окна.  
  
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
 Ненулевое значение, если сайт элемента управления был активирован, в противном случае — ноль.  
  
### <a name="remarks"></a>Примечания  
 Эта функция должна вызываться только в том случае, если пользователь переопределяет процесс создания элемента управления.  
  
 `IPersist*::Load` И `IPersist*::InitNew` методы должны вызываться после отказа быстрой активации. Элемент управления должен установить его соединения с приемниками контейнера во время быстрой активации. Тем не менее, эти подключения не отобразятся, пока `IPersist*::Load` или `IPersist*::InitNew` был вызван.  
  
##  <a name="safesetproperty"></a>  COleControlSite::SafeSetProperty  
 Задает свойства элемента управления, определяемое *dwDispID*.  
  
```  
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Определяет идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейс, устанавливаемое значение.  
  
 *vtProp*  
 Указывает тип свойства значения. Возможные значения см. в разделе "Примечания" для [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Один параметр типа, заданного параметром *vtProp*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  В отличие от `SetProperty` и `SetPropertyV`, если возникает ошибка (например, при попытке задать несуществующее свойство), исключение не создается.  
  
##  <a name="setdefaultbutton"></a>  COleControlSite::SetDefaultButton  
 Задает элемент управления как кнопка по умолчанию.  
  
```  
void SetDefaultButton(BOOL bDefault);
```  
  
### <a name="parameters"></a>Параметры  
 *bПо умолчанию*  
 Ненулевое значение, если элемент управления должен стать кнопки по умолчанию; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Элемент управления должен иметь OLEMISC_ACTSLIKEBUTTON состоянии бит.  
  
##  <a name="setdlgctrlid"></a>  COleControlSite::SetDlgCtrlID  
 Изменяет значение идентификатора элемента диалогового окна элемента управления.  
  
```  
virtual int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Новое значение идентификатора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения в предыдущем диалоговом окне item идентификатор окна. в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setfocus"></a>  COleControlSite::SetFocus  
 Устанавливает фокус на элемент управления.  
  
```  
virtual CWnd* SetFocus();  
virtual CWnd* SetFocus(LPMSG lpmsg);
```  
  
### <a name="parameters"></a>Параметры  
 *lpmsg*  
 Указатель на [структурой MSG](../../mfc/reference/msg-structure1.md). Эта структура содержит сообщение Windows вызывающей срабатывание триггера `SetFocus` запроса для элемента управления, содержащихся в текущем узле элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно, ранее имевший фокус.  
  
##  <a name="setproperty"></a>  COleControlSite::SetProperty  
 Задает свойства элемента управления, определяемое *dwDispID*.  
  
```  
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Определяет идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейс, устанавливаемое значение.  
  
 *vtProp*  
 Указывает тип свойства значения. Возможные значения см. в разделе "Примечания" для [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *...*  
 Один параметр типа, заданного параметром *vtProp*.  
  
### <a name="remarks"></a>Примечания  
 Если `SetProperty` возникает ошибка, создается исключение.  
  
 Тип исключения определяется по возвращаемому значению попытка установить свойство или метод. Если возвращается значение `DISP_E_EXCEPTION`, `COleDispatchExcpetion` создано; в противном случае — значение `COleException`.  
  
##  <a name="setpropertyv"></a>  COleControlSite::SetPropertyV  
 Задает свойства элемента управления, определяемое *dwDispID*.  
  
```  
virtual void SetPropertyV(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    va_list argList);
```  
  
### <a name="parameters"></a>Параметры  
 *dwDispID*  
 Определяет идентификатор диспетчера свойства или метода, найдено в элементе управления `IDispatch` интерфейс, устанавливаемое значение.  
  
 *vtProp*  
 Указывает тип свойства значения. Возможные значения см. в разделе "Примечания" для [COleDispatchDriver::InvokeHelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper).  
  
 *argList*  
 Указатель на список аргументов.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные параметры для метода или свойства вызван метод может быть passeed с помощью *arg_list* параметра. Если `SetProperty` возникает ошибка, создается исключение.  
  
 Тип исключения определяется по возвращаемому значению попытка установить свойство или метод. Если возвращается значение `DISP_E_EXCEPTION`, `COleDispatchExcpetion` создано; в противном случае — значение `COleException`.  
  
##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos  
 Задает размер, положение и Z-порядок управления сайта.  
  
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
 Новое положение левой части окна.  
  
 *y*  
 Новое положение верхней части окна.  
  
 *CX*  
 Новая ширина окна  
  
 *CY*  
 Новая высота окна.  
  
 *nFlags*  
 Указывает окно изменения размеров и положения флаги. Возможные значения см. в разделе "Примечания" для [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успешного выполнения, в противном случае — нуль.  
  
##  <a name="setwindowtext"></a>  COleControlSite::SetWindowText  
 Задает текст для узла элемента управления.  
  
```  
virtual void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszString*  
 Указатель на заканчивающуюся нулем строку для использования в качестве новый текст заголовка или элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция сначала пытается задать свойство Caption акций. Если свойство Caption акций не поддерживается, вместо этого устанавливается свойство Text.  
  
##  <a name="showwindow"></a>  COleControlSite::ShowWindow  
 Задает состояние отображения окна.  
  
```  
virtual BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>Параметры  
 *nCmdShow*  
 Указывает способ управления сайта для отображения. Это должен быть одно из следующих значений:  
  
- SW_HIDE скрывает это окно и передает активации на другое окно.  
  
- SW_MINIMIZE сворачивает окно и активирует окно верхнего уровня в списке системы.  
  
- Активирует SW_RESTORE и выводит на экран окно. Если окно свернуто или развернуто, Windows восстанавливает его исходный размер и положение.  
  
- SW_SHOW активирует окно и отображает его в его текущего размера и положения.  
  
- SW_SHOWMAXIMIZED активирует окно и отображает его в виде развернутого окна.  
  
- SW_SHOWMINIMIZED активирует окно и отображает его в виде значка.  
  
- SW_SHOWMINNOACTIVE свернуть окно в виде значка. Окно, который сейчас активен остается активным.  
  
- SW_SHOWNA Отображение окна в ее текущем состоянии. Окно, который сейчас активен остается активным.  
  
- SW_SHOWNOACTIVATE отображает окно в свои последние размер и положение. Окно, который сейчас активен остается активным.  
  
- Активирует SW_SHOWNORMAL и выводит на экран окно. Если окно свернуто или развернуто, Windows восстанавливает его исходный размер и положение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если окно было ранее открыто; 0, если окно ранее было скрыто.  
  
## <a name="see-also"></a>См. также  
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)
