---
title: "Класс COleControlContainer | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- custom controls [MFC], sites
- COleControlContainer class
- ActiveX control containers [C++], control site
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
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
ms.openlocfilehash: 764583d28bf71319eac5b7e51e0915ae786261a7
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolcontainer-class"></a>Класс COleControlContainer
Играет роль контейнера для элементов управления ActiveX.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|Создает объект `COleControlContainer`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|Создает узел элемента управления, размещенного в контейнере.|  
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Уведомляет все размещенные элементы управления, которые внешнее свойство изменилось.|  
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|Изменяет указанную кнопку управления.|  
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|Выбирает указанный переключатель в группе.|  
|[COleControlContainer::CreateControl](#createcontrol)|Создает размещенный элемент управления ActiveX.|  
|[COleControlContainer::CreateOleFont](#createolefont)|Создает шрифт OLE.|  
|[COleControlContainer::FindItem](#finditem)|Возвращает пользовательский узел указанного элемента управления.|  
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|Определяет, если сайт элемента управления принимает события.|  
|[COleControlContainer::GetAmbientProp](#getambientprop)|Получает указанное свойство окружения.|  
|[COleControlContainer::GetDlgItem](#getdlgitem)|Возвращает элемент указанного диалогового окна.|  
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|Получает значение элемента управления указанное диалоговое окно.|  
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|Извлекает заголовок элемента управления указанное диалоговое окно.|  
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|Определяет, поддерживает ли `WM_SETFOCUS` сообщения.|  
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|Обрабатывает сообщения, отправляемые безоконный элемент управления.|  
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Определяет состояние указанную кнопку.|  
|[COleControlContainer::OnPaint](#onpaint)|Вызывается для отрисовки части контейнера.|  
|[COleControlContainer::OnUIActivate](#onuiactivate)|Вызывается, когда элемент управления будет активирован на месте.|  
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|Вызывается при деактивации элемента управления.|  
|[COleControlContainer::ScrollChildren](#scrollchildren)|Вызывается инфраструктурой при получении сообщений прокрутки из дочернего окна.|  
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|Отправляет сообщение указанному элементу управления.|  
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|Задает значение указанного элемента управления.|  
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|Задает текст указанного элемента управления.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleControlContainer::m_crBack](#m_crback)|Цвет фона контейнера.|  
|[COleControlContainer::m_crFore](#m_crfore)|Цвет переднего плана в контейнере.|  
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Список поддерживаемых управления сайтами.|  
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|Количество элементов управления без окон.|  
|[COleControlContainer::m_pOleFont](#m_polefont)|Указатель на шрифт узел пользовательского элемента управления OLE.|  
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|Указатель узла управления записи.|  
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|Указатель на элемент управления, который в данный момент имеет фокус ввода.|  
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|Указатель на элемент управления, который в данный момент активации на месте.|  
|[COleControlContainer::m_pWnd](#m_pwnd)|Указатель на окно реализация контейнера элемента управления.|  
|[COleControlContainer::m_siteMap](#m_sitemap)|Карта сайта.|  
  
## <a name="remarks"></a>Примечания  
 Это делается, предоставляя поддержку одного или нескольких узлов элемента управления ActiveX (реализованный `COleControlSite`). `COleControlContainer`полностью реализует [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) и [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103) интерфейсы, позволяя вложенные элементы управления ActiveX для удовлетворения их квалификации, как элементы на месте.  
  
 Обычно этот класс используется в сочетании с `COccManager` и `COleControlSite` для реализации настраиваемого контейнера элементов управления ActiveX, с помощью пользовательских узлов для одного или нескольких элементов управления ActiveX.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxocc.h  
  
##  <a name="attachcontrolsite"></a>COleControlContainer::AttachControlSite  
 Вызывается платформой для создания и присоединения узла управления.  
  
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
 Идентификатор элемента управления должны быть присоединены.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите настроить этот процесс.  
  
> [!NOTE]
>  Используйте первую форму для данной функции при использовании статической привязки библиотеки MFC. Если вы динамического связывания с библиотекой MFC, следует используйте вторую форму.  
  
##  <a name="broadcastambientpropertychange"></a>COleControlContainer::BroadcastAmbientPropertyChange  
 Уведомляет все размещенные элементы управления, которые внешнее свойство изменилось.  
  
```  
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации изменяемое свойство окружения.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается инфраструктурой при изменении значения свойства окружения. Переопределите эту функцию, чтобы изменить это поведение.  
  
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
  
- **BST_INDETERMINATE** задает состояние кнопки серый, указывающее неопределенное состояние. Используйте это значение только в том случае, если кнопка имеет **BS_3STATE** или **BS_AUTO3STATE** стиль.  
  
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
 Указывает идентификатор первый переключатель в группе.  
  
 `nIDLastButton`  
 Указывает идентификатор последнего переключателя в группе.  
  
 `nIDCheckButton`  
 Указывает идентификатор переключатель для проверки.  
  
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
 Идентификатор уникального класса элемента управления.  
  
 `lpszWindowName`  
 Указатель на текст, отображаемый в элементе управления. Задает значение свойства элемента управления заголовок или текст (при наличии). Если **NULL**, свойство заголовок или текст элемента управления не изменяется.  
  
 `dwStyle`  
 Стили Windows. В списке перечислены доступные стили **примечания** раздел.  
  
 `rect`  
 Задает размер и положение элемента управления. Это может быть либо `CRect` объекта или `RECT` структуры.  
  
 `nID`  
 Указывает идентификатор элемента управления дочернего окна.  
  
 `pPersist`  
 Указатель на `CFile` содержащий постоянное состояние элемента управления. Значение по умолчанию — **NULL**, указывающее, что элемент управления инициализирует себя без восстановления состояния из любой из постоянного хранилища. Если не **NULL**, он должен быть указателем `CFile`-производный объект, содержащий постоянных данных элемента управления в форме потока или хранилища. Может, эти данные были сохранены в предыдущей активации клиента. `CFile` Может содержать другие данные, но не ее указатель чтения и записи, устанавливается на первый байт постоянные данные во время вызова `CreateControl`.  
  
 `bStorage`  
 Указывает, является ли данные в `pPersist` должен интерпретироваться как `IStorage` или `IStream` данных. Если данные в `pPersist` — это хранилище `bStorage` должно быть **TRUE**. Если данные в `pPersist` представляет собой поток `bStorage` должно быть **FALSE**. Значение по умолчанию — **FALSE**.  
  
 `bstrLicKey`  
 Необязательные данные ключа лицензии. Это данные, необходимые только для создания элементов управления, требующих выполнения лицензионный ключ. Если элемент управления поддерживает лицензирования, необходимо указать лицензионный ключ для создания элемента управления, для успешного выполнения. Значение по умолчанию — **NULL**.  
  
 *ppNewSite*  
 Указатель на узле управления, где будет размещаться создаваемого элемента управления. Значение по умолчанию — **NULL**, указывающее, что новый узел элемента управления будет автоматически создается и присоединенные к нового элемента управления.  
  
 `ppt`  
 Указатель на **ТОЧКИ** структуру, содержащую в левый верхний угол элемента управления. Размер элемента управления определяется значение *psize*. `ppt` И *psize* значения — это необязательный метод указания размера и положения элемента управления.  
  
 *psize*  
 Указатель на **размер** структуру, содержащую размер элемента управления. Левый верхний угол определяется значение `ppt`. `ppt` И *psize* значения — это необязательный метод указания размера и положения элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Только подмножество Windows `dwStyle` поддерживаемые флаги `CreateControl`:  
  
- **WS_VISIBLE** создает окно, которое изначально является видимым. Обязательно, если элемент управления видимым сразу же, как обычные окна.  
  
- **WS_DISABLED** создает окно, которое первоначально будет отключено. Отключенного окна не может получать входные данные от пользователя. Можно задать, если элемент управления имеет свойство Enabled.  
  
- `WS_BORDER`Создает окно с тонкой линии границы. Можно задать, если элемент управления имеет свойство BorderStyle.  
  
- **WS_GROUP** определяет первый элемент группы элементов управления. Пользователь может изменить фокус с одного элемента управления в группе к другому с помощью клавиш направления. Все элементы управления, определенные с помощью **WS_GROUP** стиля после первого элемента управления относятся к той же группе. Следующий элемент управления с **WS_GROUP** стиля завершает группу и запуске следующей группы.  
  
- **WS_TABSTOP** указывает элемент управления, который может получать фокус клавиатуры, когда пользователь нажимает клавишу TAB. Нажатие клавиши TAB изменяет фокус на следующий элемент управления из **WS_TABSTOP** стиля.  
  
 Создание элементов управления с размерами по умолчанию используйте вторую перегрузку.  
  
##  <a name="createolefont"></a>COleControlContainer::CreateOleFont  
 Создает шрифт OLE.  
  
```  
void CreateOleFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Параметры  
 `pFont`  
 Указатель шрифта для использования в качестве контейнера элемента управления.  
  
##  <a name="finditem"></a>COleControlContainer::FindItem  
 Находит пользовательский сайт, на котором размещается указанный элемент.  
  
```  
virtual COleControlSite* FindItem(UINT nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на индивидуализированные указанного элемента.  
  
##  <a name="freezeallevents"></a>COleControlContainer::FreezeAllEvents  
 Определяет, контейнер будет игнорировать различные события из вложенного элемента управления сайтами или принимаю условия лицензионного соглашения.  
  
```  
void FreezeAllEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Параметры  
 `bFreeze`  
 Ненулевое значение, если события будут обработаны; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Элемент управления не является обязательным для остановки обработки событий по запросу контейнера элемента управления. Он может продолжать активироваться, но все последующие события будут игнорироваться службой контейнера элемента управления.  
  
##  <a name="getambientprop"></a>COleControlContainer::GetAmbientProp  
 Возвращает значение указанного свойства окружающей среды.  
  
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
 Указатель на значение свойства окружения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="getdlgitem"></a>COleControlContainer::GetDlgItem  
 Извлекает указатель для указанного элемента управления или дочерние окна в диалоговом окне или в другом окне.  
  
```  
virtual CWnd* GetDlgItem(int nID) const;  
  
virtual void GetDlgItem(
    int nID,  
    HWND* phWnd) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Идентификатор элемента диалогового окна.  
  
 `phWnd`  
 Указатель на дескриптор объекта окна элемента указанное диалоговое окно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент диалогового окна.  
  
##  <a name="getdlgitemint"></a>COleControlContainer::GetDlgItemInt  
 Получает значение переведенный текст заданного элемента управления.  
  
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
 Указатель на логическую переменную, получающую значение успешное завершение или сбой функции ( **TRUE** указывает на успешное завершение, **FALSE** указывает на ошибку).  
  
 `bSigned`  
 Указывает ли функция изучить текст для отрицательный знак в начале и возвращают значение целого числа со знаком, если он находит. Если `bSigned` параметр **TRUE**, указывается, что значение является целочисленное значение со знаком, привести возвращаемое значение к `int` типа. Чтобы получить расширенные сведения об ошибке, вызовите [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="return-value"></a>Возвращаемое значение  
 При успешном выполнении переменная ссылается `lpTrans` равен **TRUE**, и возвращаемое значение является значением переведенный текст в элементе управления.  
  
 Если функция завершается с ошибкой, переменная ссылается `lpTrans` равен **FALSE**, и возвращаемое значение равно нулю. Обратите внимание, что, поскольку ноль возможные преобразованное значение, возвращаемое значение равно нулю не сама по себе указывают на сбой.  
  
 Если `lpTrans` — **NULL**, функция возвращает сведения об успехе или неудаче.  
  
### <a name="remarks"></a>Примечания  
 Функция преобразует возвращаемый текст путем удаления лишних пробелов в начале текста и последующего преобразования десятичных цифр. Функция останавливает перевод при достижении конца текста или встречает нечисловых знаков.  
  
 Эта функция возвращает ноль, если преобразованное значение больше, чем **INT_MAX** (для со знаком номера) или **UINT_MAX** (для чисел без знака).  
  
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
 Указывает максимальную длину в символах, строки копируются в буфер, на который указывает `lpStr`. Если длина строки превышает предел, то строка усекается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение указывает количество символов, скопировать в буфер, не включая завершающий символ null.  
  
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
 Параметр сообщения. предоставляемые Windows. Задает дополнительные сведения для конкретного сообщения. Содержимое этого параметра зависит от значения `message` параметр.  
  
 `lParam`  
 Параметр сообщения. предоставляемые Windows. Задает дополнительные сведения для конкретного сообщения. Содержимое этого параметра зависит от значения `message` параметр.  
  
 *plResult*  
 Код результата Windows. Указывает результат обработки сообщения и зависит от отправленного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе —&0;.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы настроить обработку сообщений безоконный элемент управления.  
  
##  <a name="isdlgbuttonchecked"></a>COleControlContainer::IsDlgButtonChecked  
 Определяет состояние указанную кнопку.  
  
```  
virtual UINT IsDlgButtonChecked(int nIDButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIDButton`  
 Идентификатор элемента управления button.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение, с помощью кнопки, созданные с **BS_AUTOCHECKBOX**, **BS_AUTORADIOBUTTON**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **BS_RADIOBUTTON**, или **BS_3STATE** стиль. Ниже указаны доступные значения.  
  
- **BST_CHECKED** устанавливается переключатель.  
  
- **BST_INDETERMINATE** кнопка отображается серым цветом, неопределенное состояние, указывающее (применяется только в том случае, если кнопка имеет **BS_3STATE** или **BS_AUTO3STATE** стиль).  
  
- **BST_UNCHECKED** очищен кнопки.  
  
### <a name="remarks"></a>Примечания  
 Если кнопка элемента управления с тремя состояниями, функция-член, определяет ли он недоступен, этот флажок установлен, или ни одного.  
  
##  <a name="m_crback"></a>COleControlContainer::m_crBack  
 Цвет фона контейнера.  
  
```  
COLORREF m_crBack;  
```  
  
##  <a name="m_crfore"></a>COleControlContainer::m_crFore  
 Цвет переднего плана в контейнере.  
  
```  
COLORREF m_crFore;  
```  
  
##  <a name="m_listsitesorwnds"></a>COleControlContainer::m_listSitesOrWnds  
 Список узлов элемента управления, размещенных в контейнере.  
  
```  
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;  
```  
  
##  <a name="m_nwindowlesscontrols"></a>COleControlContainer::m_nWindowlessControls  
 Количество безоконный элементы управления, размещенные в качестве контейнера элемента управления.  
  
```  
int m_nWindowlessControls;  
```  
  
##  <a name="m_polefont"></a>COleControlContainer::m_pOleFont  
 Указатель на шрифт узел пользовательского элемента управления OLE.  
  
```  
LPFONTDISP m_pOleFont;  
```  
  
##  <a name="m_psitecapture"></a>COleControlContainer::m_pSiteCapture  
 Указатель узла управления записи.  
  
```  
COleControlSite* m_pSiteCapture;  
```  
  
##  <a name="m_psitefocus"></a>COleControlContainer::m_pSiteFocus  
 Указатель на узел элемента управления, который в данный момент имеет фокус ввода.  
  
```  
COleControlSite* m_pSiteFocus;  
```  
  
##  <a name="m_psiteuiactive"></a>COleControlContainer::m_pSiteUIActive  
 Указатель на узле управления, активации на месте.  
  
```  
COleControlSite* m_pSiteUIActive;  
```  
  
##  <a name="m_pwnd"></a>COleControlContainer::m_pWnd  
 Указатель на объект окна, связанный с контейнером.  
  
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
 Ненулевое значение, если сообщение обработано; в противном случае — нуль.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы настроить процесс рисования.  
  
##  <a name="onuiactivate"></a>COleControlContainer::OnUIActivate  
 Вызывается инфраструктурой при сайт элемента управления, на который указывает `pSite`, будет активирована на месте.  
  
```  
virtual void OnUIActivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Параметры  
 `pSite`  
 Указатель на узел элемента управления будет активирован на месте.  
  
### <a name="remarks"></a>Примечания  
 Активация на месте означает, что главное меню контейнера заменяются составного меню на месте.  
  
##  <a name="onuideactivate"></a>COleControlContainer::OnUIDeactivate  
 Вызывается инфраструктурой при сайт элемента управления, на который указывает `pSite`, должен быть отключен.  
  
```  
virtual void OnUIDeactivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Параметры  
 `pSite`  
 Указатель на узел управления деактивации.  
  
### <a name="remarks"></a>Примечания  
 При получении этого уведомления контейнер должен переустановить его пользовательский интерфейс и получить фокус ввода.  
  
##  <a name="scrollchildren"></a>COleControlContainer::ScrollChildren  
 Вызывается инфраструктурой при получении сообщений прокрутки из дочернего окна.  
  
```  
virtual void ScrollChildren(
    int dx,  
    int dy);
```  
  
### <a name="parameters"></a>Параметры  
 `dx`  
 Объем, в пикселях, прокрутка по оси x.  
  
 *dy*  
 Объем, в пикселях, прокрутка по оси y.  
  
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
 Задает текст элемента управления в диалоговом окне строковое представление заданного целого.  
  
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
 Указывает, является ли `nValue` параметр знак или нет. Если этот параметр равен **TRUE**, `nValue` подписан. Если этот параметр равен **TRUE** и `nValue` меньше нуля, минус входа размещается перед первой цифрой в строке. Если этот параметр равен **FALSE**, `nValue` без знака.  
  
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

