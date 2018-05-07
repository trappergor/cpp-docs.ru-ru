---
title: Класс CTabbedPane | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
dev_langs:
- C++
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a6c42a4203fb1d0224f5f31e4123dca9a6fad65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ctabbedpane-class"></a>Класс CTabbedPane
Реализует функциональные возможности области с отделяемыми вкладками.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CTabbedPane::CTabbedPane`|Конструктор по умолчанию.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTabbedPane::DetachPane](#detachpane)|(Переопределяет [CBaseTabbedPane::DetachPane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|  
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|Включает или выключает автоматическую цветовую маркировку вкладок.|  
|[CTabbedPane::FloatTab](#floattab)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке. (Переопределяет [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CTabbedPane::GetTabArea](#gettabarea)|Возвращает размер и положение области вкладок в окне с вкладками.|  
|[CTabbedPane::GetTabWnd](#gettabwnd)||  
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|Определяет возможность переключения панели с вкладками в режим автоматического скрытия. (Переопределяет [CBaseTabbedPane::HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|  
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|Определяет, расположены ли вкладки в нижней части окна.|  
|[CTabbedPane::ResetTabs](#resettabs)|Переводит все панели с вкладками в состояние по умолчанию.|  
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|Задает список пользовательских цветов, которые могут применяться, когда включена возможность автоматической цветовой маркировки вкладок.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|Расположение вкладок в приложении по умолчанию.|  
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|Сведения о классе среды выполнения для настраиваемого объекта, производного от класса `CMFCTabCtrl`.|  
  
## <a name="remarks"></a>Примечания  
 Платформа автоматически создает экземпляр этого класса, когда пользователь прикрепляет одну панель к другой, подводя указатель мыши к заголовку второй панели. Все панели с вкладками, созданные платформой, имеют идентификатор -1.  
  
 Чтобы указать обычные вкладки вместо вкладки в стиле Outlook, передайте `AFX_CBRS_REGULAR_TABS` стиль [CDockablePane::CreateEx](../../mfc/reference/cdockablepane-class.md#createex) метод.  
  
 Если создать панель с отделяемыми вкладками, она может быть автоматически уничтожена платформой, поэтому лучше не оставлять указатель. Чтобы получить указатель на панель с вкладками, вызовите метод `CBasePane::GetParentTabbedPane`.  
  
## <a name="example"></a>Пример  
 В этом примере создается объект `CTabbedPane`. Теперь воспользуемся [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) Чтобы прикрепить дополнительные вкладки.  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),  
    TRUE, 
 (UINT) -1,  
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
    WS_CLIPCHILDREN | CBRS_LEFT |    
    CBRS_FLOAT_MULTI)) 
{  
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create  
}  
 
pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```  
  
## <a name="example"></a>Пример  
 Можно создать объект панели управления с вкладками другим способом является использование [CDockablePane::AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd). `AttachToTabWnd` Метод динамически создает объект области с вкладками, используя заданные сведения о классе среды выполнения [CDockablePane::SetTabbedPaneRTC](../../mfc/reference/cdockablepane-class.md#settabbedpanertc).  
  
 В этом примере рассматривается динамическое создание панели с вкладками, прикрепление двух вкладок друг к другу, а также преобразование второй вкладки в неотделяемую.  
  
```  
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,  
 (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxTabbedPane.h  
  
##  <a name="detachpane"></a>  CTabbedPane::DetachPane  

  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 [in] `bHide`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="enabletabautocolor"></a>  CTabbedPane::EnableTabAutoColor  
 Включает или выключает автоматическую цветовую маркировку вкладок.  
  
```  
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE` Чтобы включить автоматическое цветовую маркировку вкладок; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот статический метод для включения или отключения автоматической цветовой маркировки вкладок все панели с вкладками в приложении. Если эта функция включена, каждая вкладка заполняется свои собственные цвета. Можно найти список цветов, которые используются для закрашивания вкладки путем вызова [CMFCBaseTabCtrl::GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) метод.  
  
 Можно указать список цветов, которые будут использоваться для вкладок путем вызова [CTabbedPane::SetTabAutoColors](#settabautocolors).  
  
 По умолчанию этот параметр будет отключен.  
  
##  <a name="floattab"></a>  CTabbedPane::FloatTab  

  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 [in] `nTabID`  
 [in] `dockMethod`  
 [in] `bHide`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="gettabarea"></a>  CTabbedPane::GetTabArea  
 Возвращает размер и положение области вкладок в окне с вкладками.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectTabAreaTop`  
 Содержит размер и положение области вкладок в верхней, в экранных координатах.  
  
 [выходной] `rectTabAreaBottom`  
 Содержит размер и положение области вкладок нижней, в экранных координатах.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить, как область, на который пользователь перетаскивает закрепить. Когда пользователь перетаскивает область области вкладок в целевой области, платформа пытается добавить его в качестве новой вкладке в целевой области. В противном случае он пытается Закрепить панель части целевой области включает в себя создание нового контейнера панели с панели разделитель, который разделяет две области.  
  
 Переопределите этот метод в `CTabbedPane`-производного класса, чтобы изменить это поведение.  
  
##  <a name="gettabwnd"></a>  CTabbedPane::GetTabWnd  

  
```  
CMFCTabCtrl* GetTabWnd() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="hasautohidemode"></a>  CTabbedPane::HasAutoHideMode  

  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="istablocationbottom"></a>  CTabbedPane::IsTabLocationBottom  
 Определяет, расположены ли вкладки в нижней части окна.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если область вкладки расположена в нижней части окна с вкладками. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="m_btabsalwaystop"></a>  CTabbedPane::m_bTabsAlwaysTop  
 Расположение вкладок в приложении по умолчанию.  
  
```  
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этого статического члена `TRUE` для принудительного все вкладки в приложении, отображаемый в верхней части области с вкладками.  
  
 Это значение необходимо задать до начала создания области с вкладками.  
  
 Значение по умолчанию — `FALSE`.  
  
##  <a name="m_ptabwndrtc"></a>  CTabbedPane::m_pTabWndRTC  
 Сведения о классе среды выполнения для настраиваемого объекта, производного от класса `CMFCTabCtrl`.  
  
```  
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;  
```  
  
### <a name="remarks"></a>Примечания  
 Установите для этой переменной статический член в указатель на сведения о классе среды выполнения `CMFCTabCtrl`-производный объект при использовании пользовательских окна с вкладками в области с вкладками.  
  
##  <a name="resettabs"></a>  CTabbedPane::ResetTabs  
 Переводит все панели с вкладками в состояние по умолчанию.  
  
```  
static void ResetTabs();
```  
  
### <a name="remarks"></a>Примечания  
 Вызовите этот метод, чтобы вернуть все панели с вкладками в состояние по умолчанию. При вызове этот метод сбрасывает размеры границы и состояние автоматического цвет всех областей с вкладками.  
  
##  <a name="settabautocolors"></a>  CTabbedPane::SetTabAutoColors  
 Задает список пользовательских цветов, которые используются, если включена функция автоматической цветовой маркировки.  
  
```  
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `arColors`  
 Содержит массив цветов для задания.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы настроить список цветов, которые используются, если включена функция автоматической цветовой маркировки. — Это статическая функция и влияет на все вкладки в приложении.  
  
 Используйте [CTabbedPane::EnableTabAutoColor](#enabletabautocolor) Чтобы включить или отключить возможность автоматической цветовой маркировки.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)   
 [Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)
