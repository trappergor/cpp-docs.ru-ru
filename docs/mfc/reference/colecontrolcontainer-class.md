---
title: Класс COleControlContainer | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f33335e193997c0988cab0580c3eab612d0cc84
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852307"
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
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|Сообщает все размещенные элементы управления, внешнее свойство изменилось.|  
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|Изменяет элемент управления "Кнопка".|  
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|Выбирает указанный переключатель в группе.|  
|[COleControlContainer::CreateControl](#createcontrol)|Создает размещаемого элемента управления ActiveX.|  
|[COleControlContainer::CreateOleFont](#createolefont)|Создает шрифт OLE.|  
|[COleControlContainer::FindItem](#finditem)|Возвращает настраиваемый сайт указанного элемента управления.|  
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|Определяет, если узел управления принимает события.|  
|[COleControlContainer::GetAmbientProp](#getambientprop)|Извлекает заданное внешнее свойство.|  
|[COleControlContainer::GetDlgItem](#getdlgitem)|Возвращает элемент указанного диалогового окна.|  
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|Получает значение элемента управления указанное диалоговое окно.|  
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|Извлекает заголовок элемента управления указанное диалоговое окно.|  
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|Определяет, поддерживает ли WM_SETFOCUS сообщения.|  
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|Обрабатывает сообщения, отправляемые безоконный элемент управления.|  
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|Определяет состояние от указанной кнопки.|  
|[COleControlContainer::OnPaint](#onpaint)|Вызывается для перерисовки части контейнера.|  
|[COleControlContainer::OnUIActivate](#onuiactivate)|Вызывается, когда элемент управления будет активироваться на месте.|  
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|Вызывается при деактивации элемента управления.|  
|[COleControlContainer::ScrollChildren](#scrollchildren)|Вызывается платформой при получении сообщений прокрутки из дочернего окна.|  
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|Отправляет сообщение указанному элементу управления.|  
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|Задает значение указанного элемента управления.|  
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|Задает текст указанного элемента управления.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleControlContainer::m_crBack](#m_crback)|Цвет фона контейнера.|  
|[COleControlContainer::m_crFore](#m_crfore)|Цвет переднего плана для контейнера.|  
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|Список поддерживаемых управления сайтов.|  
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|Число размещенные элементы управления без окон.|  
|[COleControlContainer::m_pOleFont](#m_polefont)|Указатель на шрифт OLE узла пользовательского элемента управления.|  
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|Указатель на элемент управления узла записи.|  
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|Указатель на элемент управления, который в данный момент имеет фокус ввода.|  
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|Указатель на элемент управления, который используется в настоящий момент активироваться на месте.|  
|[COleControlContainer::m_pWnd](#m_pwnd)|Указатель на окно реализация контейнера элемента управления.|  
|[COleControlContainer::m_siteMap](#m_sitemap)|Карты узла.|  
  
## <a name="remarks"></a>Примечания  
 Это делается за счет поддержки одного или нескольких узлов элемента управления ActiveX (реализованный `COleControlSite`). `COleControlContainer` полностью реализует [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) и [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103) интерфейсы, обеспечивая вложенные элементы управления ActiveX, для выполнения их квалификации, как элементы на месте.  
  
 Как правило, этот класс используется в сочетании с `COccManager` и `COleControlSite` для реализации пользовательского контейнера элементов управления ActiveX, с помощью пользовательских узлов для одного или нескольких элементов управления ActiveX.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxocc.h  
  
##  <a name="attachcontrolsite"></a>  COleControlContainer::AttachControlSite  
 Вызывается платформой для создания и присоединения сайт элемента управления.  
  
```  
virtual void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);

 
void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Указатель на объект `CWnd`.  
  
 *nIDC*  
 Идентификатор элемента управления для присоединения.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, если вы хотите настроить этот процесс.  
  
> [!NOTE]
>  Используйте первую форму этой функции, если выполняется статическое связывание библиотеки MFC. При связывании динамически в библиотеку MFC, следует используйте вторую форму.  
  
##  <a name="broadcastambientpropertychange"></a>  COleControlContainer::BroadcastAmbientPropertyChange  
 Сообщает все размещенные элементы управления, внешнее свойство изменилось.  
  
```  
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>Параметры  
 *Идентификатор DISPID*  
 Идентификатор диспетчеризации внешнее свойство, которое нужно изменить.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается платформой при изменении значения внешнее свойство. Переопределите эту функцию для настройки этого поведения.  
  
##  <a name="checkdlgbutton"></a>  COleControlContainer::CheckDlgButton  
 Изменяет текущее состояние кнопки.  
  
```  
virtual void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDButton*  
 Идентификатор кнопки, чтобы изменить.  
  
 *Проверьте*  
 Указывает состояние кнопки. Ниже указаны доступные значения.  
  
- Проверяется состояние кнопки для BST_CHECKED наборов.  
  
- BST_INDETERMINATE устанавливает состояние кнопки для серым цветом, указывающее, неопределенное состояние. Это значение используется только в том случае, если кнопка имеет стиль BS_3STATE или BS_AUTO3STATE.  
  
- Наборы BST_UNCHECKED состояние кнопки, чтобы очистить.  
  
##  <a name="checkradiobutton"></a>  COleControlContainer::CheckRadioButton  
 Выбирает указанный переключатель в группе и очищает оставшихся кнопок в группе.  
  
```  
virtual void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDFirstButton*  
 Задает идентификатор для первого переключателя в группе.  
  
 *nIDLastButton*  
 Задает идентификатор последнего переключателя в группе.  
  
 *nIDCheckButton*  
 Указывает идентификатор переключателя для проверки.  
  
##  <a name="colecontrolcontainer"></a>  COleControlContainer::COleControlContainer  
 Создает объект `COleControlContainer`.  
  
```  
explicit COleControlContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 *pWnd*  
 Указатель на родительское окно контейнера элемента управления.  
  
### <a name="remarks"></a>Примечания  
 После успешного создания объекта Добавление узла пользовательского элемента управления с помощью вызова `AttachControlSite`.  
  
##  <a name="createcontrol"></a>  COleControlContainer::CreateControl  
 Создает элемент управления ActiveX, размещенного по заданному `COleControlSite` объекта.  
  
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
 *pWndCtrl*  
 Указатель на объект window, представляющий элемент управления.  
  
 *CLSID*  
 Класс уникальный идентификатор элемента управления.  
  
 *lpszWindowName*  
 Указатель на текст, отображаемый в элементе управления. Задает значение свойства заголовок или текст элемента управления (если таковые имеются). Если значение равно NULL, свойство заголовок или текст элемента управления не изменяется.  
  
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
  
 *ppNewSite*  
 Указатель на существующий узел элемента управления, где будет размещаться создаваемого элемента управления. Значение по умолчанию — NULL, указывающее, что новый сайт элемента управления будет автоматически создаваться и подключаться в новый элемент управления.  
  
 *PPT*  
 Указатель на `POINT` структуру, содержащую верхнего левого угла элемента управления. Размер элемента управления определяется по значению *psize*. *Ppt* и *psize* значения: необязательного метода задания, размер и положение элемента управления.  
  
 *psize*  
 Указатель на `SIZE` структуру, содержащую размер элемента управления. Верхнего левого угла определяется по значению *ppt*. *Ppt* и *psize* значения: необязательного метода задания, размер и положение элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Только подмножество Windows *dwStyle* флаги поддерживаются `CreateControl`:  
  
- WS_VISIBLE создает окно, которое изначально является видимым. Обязательно, если элемент управления должен отображаться сразу же, как обычные окна.  
  
- WS_DISABLED создает окно, которое изначально было отключено. Отключенного окна не может принимать входные данные от пользователя. Можно задать, если элемент управления имеет свойство Enabled.  
  
- WS_BORDER создает окно с тонкой линии границы. Можно задать, если элемент управления имеет свойства BorderStyle.  
  
- WS_GROUP задает группу элементов управления к первому элементу управления. Пользователь может изменить фокус от одного элемента управления в группе к другому с использованием ключей, направление. Все элементы управления, определенные с помощью стиля WS_GROUP после первого элемента управления, которым принадлежат той же группе. Следующий элемент управления с помощью стиля WS_GROUP завершает группе и запускается следующая команда.  
  
- WS_TABSTOP указывает элемент управления, который может получать фокус клавиатуры, когда пользователь нажимает клавишу TAB. Нажатие клавиши TAB изменяет фокус клавиатуры WS_TABSTOP стиля к следующему элементу управления.  
  
 Используйте вторую перегрузку для создания элементов управления с размером по умолчанию.  
  
##  <a name="createolefont"></a>  COleControlContainer::CreateOleFont  
 Создает шрифт OLE.  
  
```  
void CreateOleFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Параметры  
 *pFont*  
 Указатель на шрифт для использования в качестве контейнера элемента управления.  
  
##  <a name="finditem"></a>  COleControlContainer::FindItem  
 Находит настраиваемый сайт, на котором размещается указанный элемент.  
  
```  
virtual COleControlSite* FindItem(UINT nID) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор элемента, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на настраиваемый сайт указанного элемента.  
  
##  <a name="freezeallevents"></a>  COleControlContainer::FreezeAllEvents  
 Определяет контейнер будет игнорировать различные события с сайтов присоединенного элемента управления или согласны с ними.  
  
```  
void FreezeAllEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>Параметры  
 *bFreeze*  
 Ненулевое значение, если события будут обработаны; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Элемент управления не является обязательным для остановки обработки события, если запрашиваемое контейнером элемента управления. Он может продолжать активироваться, но все последующие события будут игнорироваться подсистемой контейнера элемента управления.  
  
##  <a name="getambientprop"></a>  COleControlContainer::GetAmbientProp  
 Получает значение указанного свойства окружающей среды.  
  
```  
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,  
    DISPID dispid,  
    VARIANT* pvarResult);
```  
  
### <a name="parameters"></a>Параметры  
 *pSite*  
 Указатель на сайт элемента управления, из которого будут извлекаться внешнее свойство.  
  
 *Идентификатор DISPID*  
 Идентификатор диспетчеризации требуемое внешнее свойство.  
  
 *pVarResult*  
 Указатель на значение внешнего свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
##  <a name="getdlgitem"></a>  COleControlContainer::GetDlgItem  
 Извлекает указатель для указанного элемента управления или дочерние окна в диалоговом окне или в другом окне.  
  
```  
virtual CWnd* GetDlgItem(int nID) const;  
  
virtual void GetDlgItem(
    int nID,  
    HWND* phWnd) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор извлекаемого элемента диалогового окна.  
  
 *phWnd*  
 Указатель на дескриптор окна объекта элемента указанное диалоговое окно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на элемент диалоговое окно.  
  
##  <a name="getdlgitemint"></a>  COleControlContainer::GetDlgItemInt  
 Получает значение, переведенного текста заданного элемента управления.  
  
```  
virtual UINT GetDlgItemInt(
    int nID,  
    BOOL* lpTrans,  
    BOOL bSigned) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор элемента управления.  
  
 *lpTrans*  
 Указатель на логическое переменной, получающей значение успешное завершение или сбой функции (значение TRUE указывает на успешное завершение, значение FALSE указывает на ошибку).  
  
 *bSigned*  
 Указывает ли функция изучить текст для знак «минус» в начале и возвращать целое число со знаком, если таковая найдена. Если *bSigned* параметр имеет значение TRUE, указывается, что значение извлекаемого является целое число со знаком, привести возвращаемое значение к **int** типа. Чтобы получить расширенные сведения об ошибке, вызовите [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если в случае успешного выполнения переменной указывает *lpTrans* имеет значение TRUE, и возвращает значение, преобразованное значение текста элемента управления.  
  
 Если функция завершается с ошибкой, переменная указывает *lpTrans* имеет значение FALSE, и возвращаемое значение равно нулю. Обратите внимание на то, что, поскольку ноль возможное переведенное значение, возвращаемое значение 0 не сама по себе указывает сбоя.  
  
 Если *lpTrans* имеет значение NULL, функция возвращает сведения об успехе или неудаче.  
  
### <a name="remarks"></a>Примечания  
 Функция переводит возвращаемый текст, удаление лишних пробелов в начале текста и его преобразование в десятичных цифр. Каждая функция прекращает перевод, когда он достигает конца текста или встречает нечисловых знаков.  
  
 Эта функция возвращает нуль, если преобразованное значение больше, чем INT_MAX (для чисел со знаком) или UINT_MAX (для чисел без знака).  
  
##  <a name="getdlgitemtext"></a>  COleControlContainer::GetDlgItemText  
 Извлекает текст данного элемента управления.  
  
```  
virtual int GetDlgItemText(
    int nID,  
    LPTSTR lpStr,  
    int nMaxCount) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор элемента управления.  
  
 *lpStr*  
 Указатель на текст элемента управления.  
  
 *nMaxCount*  
 Указывает максимальную длину в символах, строки копируются в буфер, на которые указывают *lpStr*. Если длина строки превышает ограничение, то строка усекается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение указывает количество символов, копируемых в буфер, не включая завершающий нуль-символ.  
  
 Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенные сведения об ошибке, вызовите [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
##  <a name="handlesetfocus"></a>  COleControlContainer::HandleSetFocus  
 Определяет, поддерживает ли WM_SETFOCUS сообщения.  
  
```  
virtual BOOL HandleSetFocus();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если контейнер обрабатывает сообщения WM_SETFOCUS; в противном случае значение равно нулю.  
  
##  <a name="handlewindowlessmessage"></a>  COleControlContainer::HandleWindowlessMessage  
 Обрабатывает сообщения окна для элементов управления без окон.  
  
```  
virtual BOOL HandleWindowlessMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* plResult);
```  
  
### <a name="parameters"></a>Параметры  
 *message*  
 Идентификатор для сообщения окна, предоставленного Windows.  
  
 *wParam*  
 Параметр сообщения; предоставляемые Windows. Задает дополнительные сведения, относящиеся к сообщению. Содержимое этого параметра зависит от значения *сообщение* параметра.  
  
 *lParam*  
 Параметр сообщения; предоставляемые Windows. Задает дополнительные сведения, относящиеся к сообщению. Содержимое этого параметра зависит от значения *сообщение* параметра.  
  
 *plResult*  
 Код результата для Windows. Указывает результат обработки сообщения и зависит от отправленного сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение в случае успеха, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы настроить обработку сообщений безоконный элемент управления.  
  
##  <a name="isdlgbuttonchecked"></a>  COleControlContainer::IsDlgButtonChecked  
 Определяет состояние от указанной кнопки.  
  
```  
virtual UINT IsDlgButtonChecked(int nIDButton) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *nIDButton*  
 Идентификатор элемента управления button.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение, с помощью кнопки, созданные с помощью BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON или BS_3STATE стиль. Ниже указаны доступные значения.  
  
- Установлен флажок кнопки BST_CHECKED.  
  
- BST_INDETERMINATE кнопка отображается серым цветом, указывающее, неопределенном состоянии (применяется только в том случае, если кнопка имеет стиль BS_3STATE или BS_AUTO3STATE).  
  
- Кнопка BST_UNCHECKED очищается.  
  
### <a name="remarks"></a>Примечания  
 Если кнопка является элементом управления тремя состояниями, функция-член, определяет ли она становится недоступной, этот флажок установлен, или ни одного.  
  
##  <a name="m_crback"></a>  COleControlContainer::m_crBack  
 Цвет фона контейнера.  
  
```  
COLORREF m_crBack;  
```  
  
##  <a name="m_crfore"></a>  COleControlContainer::m_crFore  
 Цвет переднего плана для контейнера.  
  
```  
COLORREF m_crFore;  
```  
  
##  <a name="m_listsitesorwnds"></a>  COleControlContainer::m_listSitesOrWnds  
 Список узлов элемента управления, размещаемых в контейнер.  
  
```  
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;  
```  
  
##  <a name="m_nwindowlesscontrols"></a>  COleControlContainer::m_nWindowlessControls  
 Число элементы управления без окон, размещенных в контейнере элемента управления.  
  
```  
int m_nWindowlessControls;  
```  
  
##  <a name="m_polefont"></a>  COleControlContainer::m_pOleFont  
 Указатель на шрифт OLE узла пользовательского элемента управления.  
  
```  
LPFONTDISP m_pOleFont;  
```  
  
##  <a name="m_psitecapture"></a>  COleControlContainer::m_pSiteCapture  
 Указатель на элемент управления узла записи.  
  
```  
COleControlSite* m_pSiteCapture;  
```  
  
##  <a name="m_psitefocus"></a>  COleControlContainer::m_pSiteFocus  
 Указатель на сайт элемента управления, который в данный момент имеет фокус ввода.  
  
```  
COleControlSite* m_pSiteFocus;  
```  
  
##  <a name="m_psiteuiactive"></a>  COleControlContainer::m_pSiteUIActive  
 Указатель на сайт элемента управления, который будет активироваться на месте.  
  
```  
COleControlSite* m_pSiteUIActive;  
```  
  
##  <a name="m_pwnd"></a>  COleControlContainer::m_pWnd  
 Указатель на объект окна, связанный с контейнером.  
  
```  
CWnd* m_pWnd;  
```  
  
##  <a name="m_sitemap"></a>  COleControlContainer::m_siteMap  
 Карты узла.  
  
```  
CMapPtrToPtr m_siteMap;  
```  
  
##  <a name="onpaint"></a>  COleControlContainer::OnPaint  
 Вызывается платформой для обработки запросов WM_PAINT.  
  
```  
virtual BOOL OnPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 *основного контроллера домена*  
 Указатель на контекст устройства, используемые контейнером.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение было обработано. в противном случае значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию, чтобы настроить процесс рисования.  
  
##  <a name="onuiactivate"></a>  COleControlContainer::OnUIActivate  
 Вызывается платформой при сайт элемента управления, на которые указывают *pSite*, будет активирован на месте.  
  
```  
virtual void OnUIActivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Параметры  
 *pSite*  
 Указатель на сайт элемента управления будут активироваться на месте.  
  
### <a name="remarks"></a>Примечания  
 Активация на месте означает, что главное меню контейнера заменяется на месте составного меню.  
  
##  <a name="onuideactivate"></a>  COleControlContainer::OnUIDeactivate  
 Вызывается платформой при сайт элемента управления, на которые указывают *pSite*, около должен быть отключен.  
  
```  
virtual void OnUIDeactivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>Параметры  
 *pSite*  
 Указатель на узле управления деактивации.  
  
### <a name="remarks"></a>Примечания  
 При получении этого уведомления, контейнер следует переустановить его пользовательский интерфейс и приобрести фокус.  
  
##  <a name="scrollchildren"></a>  COleControlContainer::ScrollChildren  
 Вызывается платформой при получении сообщений прокрутки из дочернего окна.  
  
```  
virtual void ScrollChildren(
    int dx,  
    int dy);
```  
  
### <a name="parameters"></a>Параметры  
 *DX*  
 Размер в пикселях прокрутку вдоль оси x.  
  
 *dy*  
 Размер в пикселях прокрутку вдоль оси y.  
  
##  <a name="senddlgitemmessage"></a>  COleControlContainer::SendDlgItemMessage  
 Отправляет сообщение указанному элементу управления.  
  
```  
virtual LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Задает идентификатор элемента управления, который получает сообщение.  
  
 *message*  
 Указывает, отправляемое сообщение.  
  
 *wParam*  
 Задает дополнительные сведения, относящиеся к сообщению.  
  
 *lParam*  
 Задает дополнительные сведения, относящиеся к сообщению.  
  
##  <a name="setdlgitemint"></a>  COleControlContainer::SetDlgItemInt  
 Задает текст элемента управления в диалоговом окне в строковое представление заданного целого значения.  
  
```  
virtual void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned);
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор элемента управления.  
  
 *nValue*  
 Целочисленное значение для отображения.  
  
 *bSigned*  
 Указывает, является ли *nValue* параметра знак или нет. Если этот параметр имеет значение TRUE, *nValue* подписан. Если этот параметр имеет значение TRUE и *nValue* меньше нуля, минус входа помещается перед первой цифрой в строке. Если этот параметр имеет значение FALSE, *nValue* не подписан.  
  
##  <a name="setdlgitemtext"></a>  COleControlContainer::SetDlgItemText  
 Задает текст указанного элемента управления, используя текст, содержащийся в *lpszString*.  
  
```  
virtual void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 *nID*  
 Идентификатор элемента управления.  
  
 *lpszString*  
 Указатель на текст элемента управления.  
  
## <a name="see-also"></a>См. также  
 [Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleControlSite](../../mfc/reference/colecontrolsite-class.md)   
 [Класс COccManager](../../mfc/reference/coccmanager-class.md)
