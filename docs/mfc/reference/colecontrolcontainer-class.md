---
title: "Класс COleControlContainer | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControlContainer
- AFXOCC/COleControlContainer
- AFXOCC/COleControlContainer::COleControlContainer
- AFXOCC/COleControlContainer::AttachControlSite
- AFXOCC/COleControlContainer::BroadcastAmbientPropertyChange
- AFXOCC/COleControlContainer::CheckDlgButton
- AFXOCC/COleControlContainer::CheckRadioButton
- AFXOCC/COleControlContainer::CreateControl
- AFXOCC/COleControlContainer::CreateOleFont
- AFXOCC/COleControlContainer::FindItem
- AFXOCC/COleControlContainer::FreezeAllEvents
- AFXOCC/COleControlContainer::GetAmbientProp
- AFXOCC/COleControlContainer::GetDlgItem
- AFXOCC/COleControlContainer::GetDlgItemInt
- AFXOCC/COleControlContainer::GetDlgItemText
- AFXOCC/COleControlContainer::HandleSetFocus
- AFXOCC/COleControlContainer::HandleWindowlessMessage
- AFXOCC/COleControlContainer::IsDlgButtonChecked
- AFXOCC/COleControlContainer::OnPaint
- AFXOCC/COleControlContainer::OnUIActivate
- AFXOCC/COleControlContainer::OnUIDeactivate
- AFXOCC/COleControlContainer::ScrollChildren
- AFXOCC/COleControlContainer::SendDlgItemMessage
- AFXOCC/COleControlContainer::SetDlgItemInt
- AFXOCC/COleControlContainer::SetDlgItemText
- AFXOCC/COleControlContainer::m_crBack
- AFXOCC/COleControlContainer::m_crFore
- AFXOCC/COleControlContainer::m_listSitesOrWnds
- AFXOCC/COleControlContainer::m_nWindowlessControls
- AFXOCC/COleControlContainer::m_pOleFont
- AFXOCC/COleControlContainer::m_pSiteCapture
- AFXOCC/COleControlContainer::m_pSiteFocus
- AFXOCC/COleControlContainer::m_pSiteUIActive
- AFXOCC/COleControlContainer::m_pWnd
- AFXOCC/COleControlContainer::m_siteMap
dev_langs: C++
helpviewer_keywords:
- COleControlContainer [MFC], COleControlContainer
- COleControlContainer [MFC], AttachControlSite
- COleControlContainer [MFC], BroadcastAmbientPropertyChange
- COleControlContainer [MFC], CheckDlgButton
- COleControlContainer [MFC], CheckRadioButton
- COleControlContainer [MFC], CreateControl
- COleControlContainer [MFC], CreateOleFont
- COleControlContainer [MFC], FindItem
- COleControlContainer [MFC], FreezeAllEvents
- COleControlContainer [MFC], GetAmbientProp
- COleControlContainer [MFC], GetDlgItem
- COleControlContainer [MFC], GetDlgItemInt
- COleControlContainer [MFC], GetDlgItemText
- COleControlContainer [MFC], HandleSetFocus
- COleControlContainer [MFC], HandleWindowlessMessage
- COleControlContainer [MFC], IsDlgButtonChecked
- COleControlContainer [MFC], OnPaint
- COleControlContainer [MFC], OnUIActivate
- COleControlContainer [MFC], OnUIDeactivate
- COleControlContainer [MFC], ScrollChildren
- COleControlContainer [MFC], SendDlgItemMessage
- COleControlContainer [MFC], SetDlgItemInt
- COleControlContainer [MFC], SetDlgItemText
- COleControlContainer [MFC], m_crBack
- COleControlContainer [MFC], m_crFore
- COleControlContainer [MFC], m_listSitesOrWnds
- COleControlContainer [MFC], m_nWindowlessControls
- COleControlContainer [MFC], m_pOleFont
- COleControlContainer [MFC], m_pSiteCapture
- COleControlContainer [MFC], m_pSiteFocus
- COleControlContainer [MFC], m_pSiteUIActive
- COleControlContainer [MFC], m_pWnd
- COleControlContainer [MFC], m_siteMap
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6d04faa904eba416b290515e5e6773ac6ef9837
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="colecontrolcontainer-class"></a>Класс COleControlContainer
Играет роль контейнера для элементов управления ActiveX.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|Создает объект `COleControlContainer`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|Создает узел элемента управления, размещенного в контейнере.|  
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Сообщает все размещенные элементы управления, которые изменилось свойство окружения.|  
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|Изменяет указанную кнопку управления.|  
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|Выбирает указанный переключатель в группе.|  
|[COleControlContainer::CreateControl](#createcontrol)|Создает размещенный элемент управления ActiveX.|  
|[COleControlContainer::CreateOleFont](#createolefont)|Создает шрифт OLE.|  
|[COleControlContainer::FindItem](#finditem)|Возвращает настраиваемый сайт указанного элемента управления.|  
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|Определяет, если узел элемента управления прием событий.|  
|[COleControlContainer::GetAmbientProp](#getambientprop)|Получает указанное свойство окружения.|  
|[COleControlContainer::GetDlgItem](#getdlgitem)|Возвращает элемент указанного диалогового окна.|  
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|Получает значение указанного диалогового окна элемента управления.|  
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|Получает заголовок элемента управления указанное диалоговое окно.|  
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|Определяет, поддерживает ли `WM_SETFOCUS` сообщения.|  
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|Обрабатывает сообщения, отправляемые управления без окна.|  
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Определяет, входит в указанную кнопку.|  
|[COleControlContainer::OnPaint](#onpaint)|Вызывается для перерисовки части контейнера.|  
|[COleControlContainer::OnUIActivate](#onuiactivate)|Вызывается, когда элемент управления будет активирован на месте.|  
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|Вызывается при деактивации элемента управления.|  
|[COleControlContainer::ScrollChildren](#scrollchildren)|Вызывается платформой при получении сообщения прокрутки от дочернего окна.|  
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|Отправляет сообщение указанному элементу управления.|  
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|Задает значение указанного элемента управления.|  
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|Задает текст указанного элемента управления.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlContainer::m_crBack](#m_crback)|Цвет фона контейнера.|  
|[COleControlContainer::m_crFore](#m_crfore)|Цвет переднего плана контейнера.|  
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Список поддерживаемых управления сайтов.|  
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|Число размещенных элементов управления без окон.|  
|[COleControlContainer::m_pOleFont](#m_polefont)|Указатель шрифта OLE узла пользовательского элемента управления.|  
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|Указатель на элемент управления узла записи.|  
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|Указатель на элемент управления, который в данный момент имеет фокус ввода.|  
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|Указатель на элемент управления в данный момент активации на месте.|  
|[COleControlContainer::m_pWnd](#m_pwnd)|Указатель на окно реализация контейнера элемента управления.|  
|[COleControlContainer::m_siteMap](#m_sitemap)|Карта сайта.|  
  
## <a name="remarks"></a>Примечания  
 Это можно сделать, предоставляя поддержку одного или нескольких узлов элемента управления ActiveX (реализуемый `COleControlSite`). `COleControlContainer`полностью реализует [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) и [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103) интерфейсы, позволяя вложенные элементы управления ActiveX для удовлетворения своих квалификации, как элементы на месте.  
  
 Как правило, этот класс используется в сочетании с `COccManager` и `COleControlSite` для реализации пользовательских контейнеров элементов управления ActiveX, с помощью настраиваемых сайтов для одного или нескольких элементов управления ActiveX.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxocc.h  
  
##  <a name="attachcontrolsite"></a>COleControlContainer::AttachControlSite  
 Вызывается платформой для создания и присоединить узел элемента управления.  
  
```  
virtual void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);

 
void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на объект `CWnd`.  
  
 `nIDC`  
 Идентификатор элемента управления для присоединения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите настроить этот процесс.  
  
> [!NOTE]
>  Используйте первую форму этой функции, если выполняется статическое связывание с библиотекой MFC. При связывании динамически с библиотекой MFC, следует используйте вторую форму.  
  
##  <a name="broadcastambientpropertychange"></a>COleControlContainer::BroadcastAmbientPropertyChange  
 Сообщает все размещенные элементы управления, которые изменилось свойство окружения.  
  
```  
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации изменяемое свойство окружения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается платформой при изменении значения внешнего свойства. Переопределите эту функцию для настройки этого поведения.  
  
##  <a name="checkdlgbutton"></a>COleControlContainer::CheckDlgButton  
 Изменяет текущее состояние кнопки.  
  
```  
virtual void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDButton`  
 Идентификатор изменяемой кнопки.  
  
 `nCheck`  
 Указывает состояние кнопки. Ниже указаны доступные значения.  
  
- **BST_CHECKED** задает состояние кнопки checked.  
  
- **BST_INDETERMINATE** задает состояние кнопки выделена серым цветом, указывающее, неопределенное состояние. Используйте это значение только в том случае, если кнопка имеет **BS_3STATE** или **BS_AUTO3STATE** стиля.  
  
- **BST_UNCHECKED** задает состояние кнопки снят.  
  
##  <a name="checkradiobutton"></a>COleControlContainer::CheckRadioButton  
 Выбирает указанный переключатель в группе и очищает оставшихся кнопок в группе.  
  
```  
virtual void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDFirstButton`  
 Задает идентификатор для первого переключателя в группе.  
  
 `nIDLastButton`  
 Задает идентификатор последнего переключателя в группе.  
  
 `nIDCheckButton`  
 Указывает идентификатор переключателя для проверки.  
  
##  <a name="colecontrolcontainer"></a>COleControlContainer::COleControlContainer  
 Создает объект `COleControlContainer`.  
  
```  
explicit COleControlContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указатель на родительское окно контейнера элемента управления.  
  
### <a name="remarks"></a>Примечания  
 После успешного создания объекта добавить узел пользовательского элемента управления с помощью вызова `AttachControlSite`.  
  
##  <a name="createcontrol"></a>COleControlContainer::CreateControl  
 Создает элемент управления ActiveX, размещенных на заданный `COleControlSite` объекта.  
  
```  
BOOL CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    UINT nID,  
    CFile* pPersist =NULL,  
    BOOL bStorage =FALSE,  
    BSTR bstrLicKey =NULL,  
    COleControlSite** ppNewSite =NULL);

 
BOOL CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const POINT* ppt,  
    const SIZE* psize,  
    UINT nID,  
    CFile* pPersist =NULL,  
    BOOL bStorage =FALSE,  
    BSTR bstrLicKey =NULL,  
    COleControlSite** ppNewSite =NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pWndCtrl`  
 Указатель на объект window, представляющий элемент управления.  
  
 `clsid`  
 Класс уникальный идентификатор элемента управления.  
  
 `lpszWindowName`  
 Указатель на текст, отображаемый в элементе управления. Задает значение свойства заголовок или текст элемента управления (если таковые имеются). Если **NULL**, свойство заголовок или текст элемента управления не изменяется.  
  
 `dwStyle`  
 Стили Windows. Доступные стили, которые будут отображаться в **примечания** раздела.  
  
 `rect`  
 Задает размер и положение элемента управления. Это может быть либо `CRect` объекта или `RECT` структуры.  
  
 `nID`  
 Указывает идентификатор элемента управления дочернего окна.  
  
 `pPersist`  
 Указатель на `CFile` содержащий постоянное состояние для элемента управления. Значение по умолчанию — **NULL**, указывающее, что элемент управления инициализирует себя без восстановления свое состояние из любого из постоянного хранилища. В противном случае **NULL**, он должен быть указателем на `CFile`-производный объект, который содержит постоянных данных элемента управления в виде потока или хранилища. Удалось, эти данные были сохранены в предыдущей активации клиента. `CFile` Может содержать другие данные, но не устанавливается на первый байт постоянные данные во время вызова для чтения и записи указатель `CreateControl`.  
  
 `bStorage`  
 Указывает, является ли данные в `pPersist` должен интерпретироваться как `IStorage` или `IStream` данных. Если данные в `pPersist` — это хранилище `bStorage` должно быть **TRUE**. Если данные в `pPersist` представляет собой поток `bStorage` должно быть **FALSE**. Значение по умолчанию — **FALSE**.  
  
 `bstrLicKey`  
 Необязательные данные ключа лицензии. Эти данные требуется только для создания элементов управления, требующих ключ лицензии во время выполнения. Если элемент управления поддерживает лицензирования, необходимо указать лицензионный ключ для создания элемента управления для успешного выполнения. Значение по умолчанию — **NULL**.  
  
 *ppNewSite*  
 Указатель на узле управления, где будет размещаться элемент управления, в процессе создания. Значение по умолчанию — **NULL**, указывающее, что новый сайт элемента управления будет автоматически создается и присоединяется к нового элемента управления.  
  
 `ppt`  
 Указатель на **ТОЧКИ** структуру, содержащую верхнего левого угла элемента управления. Размер элемента управления определяется по значению *psize*. `ppt` И *psize* значения — это дополнительный способ задания размера и положения элемента управления.  
  
 *psize*  
 Указатель на **размер** структуру, содержащую размер элемента управления. Значение определяется верхнего левого угла `ppt`. `ppt` И *psize* значения — это дополнительный способ задания размера и положения элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Только подмножество Windows `dwStyle` поддерживаемых флаги `CreateControl`:  
  
- **WS_VISIBLE** создает окно, которое изначально является видимым. Обязательно, если элемент управления видимым сразу же, как обычные окна.  
  
- **WS_DISABLED** создает окно, которое изначально отключены. Отключенного окна не может получать входные данные от пользователя. Можно задать, если элемент управления имеет свойство Enabled.  
  
- `WS_BORDER`Создает окно с тонкой линии границы. Можно задать, если элемент управления имеет свойства BorderStyle.  
  
- **WS_GROUP** определяет первый элемент группы элементов управления. Пользователь может изменить фокус от одного элемента управления в группе к другому с помощью клавиш направления. Все элементы управления, имеющий **WS_GROUP** стиль после первого элемента управления принадлежать одной группе. Следующий элемент управления с **WS_GROUP** стиль завершает группу и запуске следующей группы.  
  
- **WS_TABSTOP** указывает элемент управления, который может получать фокус клавиатуры, когда пользователь нажимает клавишу TAB. Нажатие клавиши TAB изменяет фокус на следующий элемент управления из **WS_TABSTOP** стиля.  
  
 Создание элементов управления с размерами по умолчанию используйте вторую перегрузку.  
  
##  <a name="createolefont"></a>COleControlContainer::CreateOleFont  
 Создает шрифт OLE.  
  
```  
void CreateOleFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Параметры  
 `pFont`  
 Указатель на шрифт, который будет использоваться в качестве контейнера элемента управления.  
  
##  <a name="finditem"></a>COleControlContainer::FindItem  
 Находит настраиваемый сайт, на котором размещается указанный элемент.  
  
```  
virtual COleControlSite* FindItem(UINT nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на настраиваемый сайт указанного элемента.  
  
##  <a name="freezeallevents"></a>COleControlContainer::FreezeAllEvents  
 Определяет, контейнер будет игнорировать различные события из вложенного элемента управления сайтов или принимаю условия лицензионного соглашения.  
  
```  
void FreezeAllEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Параметры  
 `bFreeze`  
 Ненулевое значение, если события будут обработаны; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Элемент управления не является обязательным для остановки вызова событий, если запрашиваемое контейнером элемента управления. Он может продолжать активироваться, но все последующие события будут игнорироваться контейнера элемента управления.  
  
##  <a name="getambientprop"></a>COleControlContainer::GetAmbientProp  
 Получает значение указанного свойства окружения.  
  
```  
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,  
    DISPID dispid,  
    VARIANT* pvarResult);
```  
  
### <a name="parameters"></a>Параметры  
 `pSite`  
 Указатель на узел элемента управления, из которого требуется извлечь свойства окружения.  
  
 `dispid`  
 Идентификатор диспетчеризации требуемое внешнее свойство.  
  
 *pVarResult*  
 Указатель на значение внешнего свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="getdlgitem"></a>COleControlContainer::GetDlgItem  
 Извлекает указатель на указанный элемент управления или дочернее окно в диалоговом окне или в другом окне.  
  
```  
virtual CWnd* GetDlgItem(int nID) const;  
  
virtual void GetDlgItem(
    int nID,  
    HWND* phWnd) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор извлекаемого элемента диалогового окна.  
  
 `phWnd`  
 Указатель на дескриптор объекта окна элемента указанного диалогового окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на окно элемента диалогового окна.  
  
##  <a name="getdlgitemint"></a>COleControlContainer::GetDlgItemInt  
 Получает значение переведенный текст данного элемента управления.  
  
```  
virtual UINT GetDlgItemInt(
    int nID,  
    BOOL* lpTrans,  
    BOOL bSigned) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления.  
  
 `lpTrans`  
 Указатель на переменную типа Boolean, получающую значение успешных завершений и сбоев функция ( **TRUE** указывает на успешное завершение, **FALSE** указывает на ошибку).  
  
 `bSigned`  
 Определяет, следует функция анализирует текст, знак «минус» в начале и возвращают значение целого числа со знаком, при обнаружении. Если `bSigned` параметр **TRUE**, указывается, что получаемое значение является значение целого числа со знаком, привести возвращаемое значение к `int` типа. Чтобы получить расширенные сведения об ошибке, вызовите [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении переменная указывает `lpTrans` равно **TRUE**, и возвращаемое значение является значением переведенный текст элемента управления.  
  
 Если функция завершается с ошибкой, переменная указывает `lpTrans` равно **FALSE**, и возвращаемое значение равно нулю. Обратите внимание, что, поскольку ноль возможных преобразованное значение, возвращаемое значение равно нулю не сам по себе указывают на сбой.  
  
 Если `lpTrans` — **NULL**, функция возвращает сведения об успешном или неуспешном завершении отсутствуют.  
  
### <a name="remarks"></a>Примечания  
 Функция преобразует возвращаемый текст путем удаления лишних пробелов в начале текста и затем преобразования десятичных цифр. Функция останавливает преобразования при достижении конца текста или встречает нечисловых знаков.  
  
 Эта функция возвращает ноль, если преобразованное значение больше, чем **INT_MAX** (для числа со знаком) или **UINT_MAX** (для чисел без знака).  
  
##  <a name="getdlgitemtext"></a>COleControlContainer::GetDlgItemText  
 Извлекает текст данного элемента управления.  
  
```  
virtual int GetDlgItemText(
    int nID,  
    LPTSTR lpStr,  
    int nMaxCount) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления.  
  
 `lpStr`  
 Указатель на текст элемента управления.  
  
 `nMaxCount`  
 Указывает максимальную длину в символах, строки копируются в буфер, который указывает `lpStr`. Если длина строки превышает предел, то строка усекается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение указывает число символов, скопировать в буфер, не включая завершающий символ null.  
  
 Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенные сведения об ошибке, вызовите [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
##  <a name="handlesetfocus"></a>COleControlContainer::HandleSetFocus  
 Определяет, поддерживает ли `WM_SETFOCUS` сообщения.  
  
```  
virtual BOOL HandleSetFocus();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если контейнер `WM_SETFOCUS` сообщения; в противном случае — нуль.  
  
##  <a name="handlewindowlessmessage"></a>COleControlContainer::HandleWindowlessMessage  
 Обрабатывает сообщения окна для элементов управления без окон.  
  
```  
virtual BOOL HandleWindowlessMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* plResult);
```  
  
### <a name="parameters"></a>Параметры  
 `message`  
 Идентификатор для окна сообщения, предоставляемые Windows.  
  
 `wParam`  
 Параметр сообщения. предоставляемые Windows. Задает дополнительные сведения для конкретного сообщения. Содержимое этого параметра зависит от значения `message` параметра.  
  
 `lParam`  
 Параметр сообщения. предоставляемые Windows. Задает дополнительные сведения для конкретного сообщения. Содержимое этого параметра зависит от значения `message` параметра.  
  
 *plResult*  
 Код результата Windows. Указывает результат обработки сообщения и зависит от отправляемого сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для обработки сообщения без окна элемента управления.  
  
##  <a name="isdlgbuttonchecked"></a>COleControlContainer::IsDlgButtonChecked  
 Определяет, входит в указанную кнопку.  
  
```  
virtual UINT IsDlgButtonChecked(int nIDButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIDButton`  
 Идентификатор элемента управления button.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение, с помощью кнопки, созданных с помощью **BS_AUTOCHECKBOX**, **BS_AUTORADIOBUTTON**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **BS_RADIOBUTTON**, или **BS_3STATE** стиля. Ниже указаны доступные значения.  
  
- **BST_CHECKED** кнопки.  
  
- **BST_INDETERMINATE** кнопка отображается серым цветом, неопределенное состояние, указывающее (применяется только в том случае, если эта кнопка имеет **BS_3STATE** или **BS_AUTO3STATE** стиль).  
  
- **BST_UNCHECKED** кнопку снят.  
  
### <a name="remarks"></a>Примечания  
 Если кнопки элемента управления с тремя состояниями, функция-член, определяет ли он недоступен, этот флажок установлен, и ни одного.  
  
##  <a name="m_crback"></a>COleControlContainer::m_crBack  
 Цвет фона контейнера.  
  
```  
COLORREF m_crBack;  
```  
  
##  <a name="m_crfore"></a>COleControlContainer::m_crFore  
 Цвет переднего плана контейнера.  
  
```  
COLORREF m_crFore;  
```  
  
##  <a name="m_listsitesorwnds"></a>COleControlContainer::m_listSitesOrWnds  
 Список узлов элемента управления, размещенных в контейнере.  
  
```  
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;  
```  
  
##  <a name="m_nwindowlesscontrols"></a>COleControlContainer::m_nWindowlessControls  
 Количество элементов управления без окон, размещаемую в контейнере элемента управления.  
  
```  
int m_nWindowlessControls;  
```  
  
##  <a name="m_polefont"></a>COleControlContainer::m_pOleFont  
 Указатель шрифта OLE узла пользовательского элемента управления.  
  
```  
LPFONTDISP m_pOleFont;  
```  
  
##  <a name="m_psitecapture"></a>COleControlContainer::m_pSiteCapture  
 Указатель на элемент управления узла записи.  
  
```  
COleControlSite* m_pSiteCapture;  
```  
  
##  <a name="m_psitefocus"></a>COleControlContainer::m_pSiteFocus  
 Указатель на узел элемента управления, который в данный момент имеет фокус ввода.  
  
```  
COleControlSite* m_pSiteFocus;  
```  
  
##  <a name="m_psiteuiactive"></a>COleControlContainer::m_pSiteUIActive  
 Указатель на сайт управления, активации на месте.  
  
```  
COleControlSite* m_pSiteUIActive;  
```  
  
##  <a name="m_pwnd"></a>COleControlContainer::m_pWnd  
 Указатель на объект window, связанные с контейнером.  
  
```  
CWnd* m_pWnd;  
```  
  
##  <a name="m_sitemap"></a>COleControlContainer::m_siteMap  
 Карта сайта.  
  
```  
CMapPtrToPtr m_siteMap;  
```  
  
##  <a name="onpaint"></a>COleControlContainer::OnPaint  
 Вызывается платформой для обработки `WM_PAINT` запросов.  
  
```  
virtual BOOL OnPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 `pDC`  
 Указатель на контекст устройства, используемые контейнером.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение было обработано; в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для настройки процесса рисования.  
  
##  <a name="onuiactivate"></a>COleControlContainer::OnUIActivate  
 Вызывается платформой при сайта элемента управления, на который указывает `pSite`, должна быть активирована на месте.  
  
```  
virtual void OnUIActivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Параметры  
 `pSite`  
 Указатель на узел элемента управления будет активирован на месте.  
  
### <a name="remarks"></a>Примечания  
 Активация на месте означает, что главного меню контейнера заменяются на месте составного меню.  
  
##  <a name="onuideactivate"></a>COleControlContainer::OnUIDeactivate  
 Вызывается платформой при сайта элемента управления, на который указывает `pSite`, будут отключены.  
  
```  
virtual void OnUIDeactivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Параметры  
 `pSite`  
 Указатель на узел управления деактивации.  
  
### <a name="remarks"></a>Примечания  
 При получении этого уведомления, контейнер следует переустановить его пользовательский интерфейс и получить фокус ввода.  
  
##  <a name="scrollchildren"></a>COleControlContainer::ScrollChildren  
 Вызывается платформой при получении сообщения прокрутки от дочернего окна.  
  
```  
virtual void ScrollChildren(
    int dx,  
    int dy);
```  
  
### <a name="parameters"></a>Параметры  
 `dx`  
 Размер в пикселях прокрутки по оси x.  
  
 *dy*  
 Размер в пикселях прокрутки по оси y.  
  
##  <a name="senddlgitemmessage"></a>COleControlContainer::SendDlgItemMessage  
 Отправляет сообщение указанному элементу управления.  
  
```  
virtual LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Задает идентификатор элемента управления, который получает сообщение.  
  
 `message`  
 Задает отправку сообщения.  
  
 `wParam`  
 Задает дополнительные сведения для конкретного сообщения.  
  
 `lParam`  
 Задает дополнительные сведения для конкретного сообщения.  
  
##  <a name="setdlgitemint"></a>COleControlContainer::SetDlgItemInt  
 Задает текст элемента управления в диалоговом окне в строковое представление указанного целочисленного значения.  
  
```  
virtual void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления.  
  
 `nValue`  
 Целочисленное значение для отображения.  
  
 `bSigned`  
 Указывает, является ли `nValue` параметр знак или нет. Если этот параметр имеет **TRUE**, `nValue` подписан. Если этот параметр имеет **TRUE** и `nValue` меньше нуля, минус входа размещается перед первой цифрой в строке. Если этот параметр имеет **FALSE**, `nValue` не подписан.  
  
##  <a name="setdlgitemtext"></a>COleControlContainer::SetDlgItemText  
 Задает текст указанного элемента управления, используя текст, содержащийся в `lpszString`.  
  
```  
virtual void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента управления.  
  
 `lpszString`  
 Указатель на текст элемента управления.  
  
## <a name="see-also"></a>См. также  
 [CCmdTarget-класс](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleControlSite](../../mfc/reference/colecontrolsite-class.md)   
 [Класс COccManager](../../mfc/reference/coccmanager-class.md)
