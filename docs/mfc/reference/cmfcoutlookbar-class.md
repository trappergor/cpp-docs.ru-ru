---
title: Класс CMFCOutlookBar | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBar [MFC], AllowDestroyEmptyTabbedPane
- CMFCOutlookBar [MFC], CanAcceptPane
- CMFCOutlookBar [MFC], CanSetCaptionTextToTabName
- CMFCOutlookBar [MFC], Create
- CMFCOutlookBar [MFC], CreateCustomPage
- CMFCOutlookBar [MFC], DoesAllowDynInsertBefore
- CMFCOutlookBar [MFC], FloatTab
- CMFCOutlookBar [MFC], GetButtonsFont
- CMFCOutlookBar [MFC], GetTabArea
- CMFCOutlookBar [MFC], IsMode2003
- CMFCOutlookBar [MFC], OnAfterAnimation
- CMFCOutlookBar [MFC], OnBeforeAnimation
- CMFCOutlookBar [MFC], OnScroll
- CMFCOutlookBar [MFC], RemoveCustomPage
- CMFCOutlookBar [MFC], SetButtonsFont
- CMFCOutlookBar [MFC], SetMode2003
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5640f634276f87d0a41633354a7dde0ed65a2940
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372499"
---
# <a name="cmfcoutlookbar-class"></a>Класс CMFCOutlookBar
Область со вкладками, которая имеет внешний вид области **Область переходов** в Microsoft Outlook 2000 или Outlook 2003. `CMFCOutlookBar` Объект содержит [класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md) объекта и ряд вкладок. Вкладки могут быть либо [класса CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) объектов или `CWnd`-производных объектов. Пользователю панель Outlook отображается как последовательность кнопок и область отображения. Когда пользователь нажимает кнопку, отображается соответствующая область элемента управления или кнопки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|Конструктор по умолчанию.|  
|`CMFCOutlookBar::~CMFCOutlookBar`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Указывает, можно ли удалить пустой области с вкладками. (Переопределяет [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Определяет, является ли другую панель можно закрепить область панели Outlook. (Переопределяет CDockablePane::CanAcceptPane).|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Определяет, отображать ли заголовок для области с вкладками тот же текст в качестве активной вкладки. (Переопределяет [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|  
|[CMFCOutlookBar::Create](#create)|Создает элемент управления панель Outlook.|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Создание настраиваемой вкладки панели Outlook.|  
|`CMFCOutlookBar::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, является ли пользователь можно закрепить панель элементов управления на внешней границе панели Outlook.|  
|[CMFCOutlookBar::FloatTab](#floattab)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке. (Переопределяет [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Возвращает шрифт текста на кнопках панели Outlook.|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Возвращает размер и положение области вкладки на панели Outlook. (Переопределяет [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|  
|`CMFCOutlookBar::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Определяет, имитирует ли поведение панели Outlook, Microsoft Office Outlook 2003 (см. примечания).|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Вызывается методом [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) после задания активной вкладки с помощью анимации.|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Вызывается методом [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) перед вкладки страницы задается в качестве активной вкладки с помощью анимации.|  
|[CMFCOutlookBar::OnScroll](#onscroll)|Вызывается платформой при прокрутке панели Outlook вверх или вниз.|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Удаляет настраиваемой вкладки панели Outlook.|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Задает шрифт текста, кнопок панели Outlook.|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Указывает, имитирует ли поведение панели Outlook, Outlook 2003 (см. примечания).|  
  
## <a name="remarks"></a>Примечания  
 Пример панели Outlook см. в разделе [образце OutlookDemo: приложение MFC OutlookDemo](../../visual-cpp-samples.md).  
  
## <a name="implementing-the-outlook-bar"></a>Реализация панели Outlook  
 Для использования элемента управления `CMFCOutlookBar` в своем приложении выполните следующие действия:  
  
1.  Внедрите объект `CMFCOutlookBar` в класс окна главного фрейма.  
  
 ```  
    class CMainFrame : public CMDIFrameWnd  
 { ...  
    CMFCOutlookBar m_wndOutlookBar;  
    CMFCOutlookBarPane m_wndOutlookPane;  
 ... };  
 ```  
2.  При обработке `WM_CREATE` сообщения в главного фрейма вызова [CMFCOutlookBar::Create](#create) метод для создания панели управления "Вкладка" Outlook.  
  
 ```  
    m_wndOutlookBar.Create (_T("Shortcuts"),
    this,
    CRect (0,
    0,
    100,
    100),
    ID_VIEW_OUTLOOKBAR,
    WS_CHILD | WS_VISIBLE | CBRS_LEFT);

 ```  
3.  Получение указателя на базовый `CMFCOutlookBarTabCtrl` с помощью [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).  
  
 ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();

 ```  
4.  Создание [CMFCOutlookBarPane класса](../../mfc/reference/cmfcoutlookbarpane-class.md) объект для каждой вкладки, содержащей кнопки.  
  
 ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar,
    AFX_DEFAULT_TOOLBAR_STYLE,
    ID_OUTLOOK_PANE_GENERAL,
    AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);
*// make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);
*// add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About",
    ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open",
    ID_FILE_OPEN);

 ```  
5.  Вызовите [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) для добавления каждой новой вкладке. Задать `bDetachable` параметр `FALSE` вносить неотделяемые страницы. Также можно использовать [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) добавления отделяемые страниц.  
  
 ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1,
    TRUE);

 ```  
6.  Добавление `CWnd`-производного элемента управления (например, [класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)) в виде вкладки, создание элемента управления и вызвать [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) Добавление на панель Outlook.  
  
> [!NOTE]
>  Следует использовать уникальные идентификаторы элементов управления для каждого [класса CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) объекта и для каждого `CWnd`-производного объекта.  
  
 Чтобы динамически добавлять или удалять новые страницы во время выполнения, используйте [CMFCOutlookBar::CreateCustomPage](#createcustompage) и [CMFCOutlookBar::RemoveCustomPage](#removecustompage).  
  
## <a name="outlook-2003-mode"></a>Режим Outlook 2003  
 В режиме Outlook 2003 кнопок, расположенные в нижней части область панели Outlook. Если имеется достаточно места для отображения кнопок, они отображаются как значки в области панели инструментов в нижней части области.  
  
 Используйте [CMFCOutlookBar::SetMode2003](#setmode2003) для перехода в режим Outlook 2003. Используйте [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) присвоить точечного рисунка, который содержит значки, которые отображаются в нижней части панели Outlook. Значки в битовой карте должны быть упорядочены по клавише tab.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxoutlookbar.h  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CMFCOutlookBar::AllowDestroyEmptyTabbedPane  
 Указывает, можно ли удалить пустой области с вкладками.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если пустая область с вкладками может быть уничтожено; в противном случае `FALSE`. Реализация по умолчанию всегда возвращает значение `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Если не может быть уничтожен пустая область с вкладками, платформа скрывает его вместо него.  
  
##  <a name="canacceptpane"></a>  CMFCOutlookBar::CanAcceptPane  
 Определяет, является ли другую панель можно закрепить область панели Outlook.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на другую панель, расположенной в эту область.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если другую панель можно закрепить область панели Outlook; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если панель Outlook находится в режиме Outlook 2003, закрепления не поддерживается, поэтому возвращаемое значение `FALSE`.  
  
 Если `pBar` параметр `NULL`, этот метод возвращает `FALSE`.  
  
 В противном случае этот метод работает как базовый метод [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane), за исключением того, что даже если закрепление не включена, панель Outlook можно по-прежнему включить другую панель Outlook можно закреплять на него.  
  
##  <a name="cansetcaptiontexttotabname"></a>  CMFCOutlookBar::CanSetCaptionTextToTabName  
 Определяет, отображать ли заголовок для области с вкладками тот же текст в качестве активной вкладки.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если панели заголовка окна Outlook автоматически присваивается текста активной вкладки; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) для включения или отключения этой функции.  
  
 Этот параметр всегда включен в режиме Outlook 2003.  
  
##  <a name="create"></a>  CMFCOutlookBar::Create  
 Создает элемент управления панель Outlook.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszCaption`  
 Задает заголовок окна.  
  
 [in] `pParentWnd`  
 Задает указатель на родительское окно. Оно не должно быть NULL.  
  
 [in] `rect`  
 Задает размер и положение в пикселях на панели outlook.  
  
 [in] `nID`  
 Указывает идентификатор элемента управления. Должны отличаться от другого элемента управления идентификаторы, используемые в приложении.  
  
 [in] `dwStyle`  
 Указывает стиль панели требуемого элемента управления. Возможные значения см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `dwControlBarStyle`  
 Указывает специальные стили, определенные в библиотеке.  
  
 [in] `pContext`  
 Создание контекста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CMFCOutlookBar` объекта в два этапа. Сначала вызовите конструктор, а затем вызвать `Create`, который создает элемент управления панель outlook и прикрепляет его к `CMFCOutlookBar` объекта.  
  
 В разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) список доступных стилей определенные библиотеки по `dwControlBarStyle`.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Create` метод `CMFCOutlookBar` класса. Этот фрагмент кода является частью [пример нескольких представлениях Outlook](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>  CMFCOutlookBar::CreateCustomPage  
 Создание настраиваемой вкладки панели Outlook.  
  
```  
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,  
    BOOL bActivatePage=TRUE,  
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,  
    BOOL bEnableTextLabels=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszPageName`  
 Подпись.  
  
 [in] `bActivatePage`  
 Если `TRUE`, страница становится активной после их создания.  
  
 [in] `dwEnabledDocking`  
 Сочетание CBRS_ALIGN_ флагов, указывающее, включено закрепление сторон при отсоединении страницы.  
  
 [in] `bEnableTextLabels`  
 Если `TRUE`, текстовые метки включены для кнопок, которые находятся на странице.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный страницу или `NULL` , если не удалось создать.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы разрешить пользователям создавать пользовательские страницы панели Outlook. Можно создать до 100 страниц в приложении. Элемент управления страницы, запустите идентификаторы в число 0xF000. Создание завершается сбоем, если общее число пользовательских страниц панели Outlook превышает 100.  
  
 Используйте [CMFCOutlookBar::RemoveCustomPage](#removecustompage) удалить настраиваемые страницы.  
  
##  <a name="doesallowdyninsertbefore"></a>  CMFCOutlookBar::DoesAllowDynInsertBefore  
 Указывает, является ли пользователь можно закрепить панель на внешней границе панели Outlook.  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает `DoesAllowDynInsertBefore` метод при поиске расположения закрепить динамической области. Если функция возвращает `FALSE`, платформа не допускает закрепление любой динамического панели во внешние края панели.  
  
 Как правило панель Outlook создается как статический элемент управления не с плавающей запятой. Можно переопределить эту функцию в производном классе и возвращать `TRUE` это поведение можно изменить.  
  
> [!NOTE]
>  Поскольку динамических панелей проверить состояние закрепленных панелей статических при закрепления, должны закрепляться динамических панелей после статических областей, по возможности.  
  
##  <a name="floattab"></a>  CMFCOutlookBar::FloatTab  
 Преобразует панель в.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на панели, чтобы число с плавающей запятой.  
  
 [in] `nTabID`  
 Отсчитываемый от нуля индекс вкладки в тип float.  
  
 [in] `dockMethod`  
 Указывает метод, чтобы делать на панели с плавающей запятой.  Дополнительные сведения см. в разделе [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).  
  
 [in] `bHide`  
 `TRUE` Чтобы скрыть область перед с плавающей запятой; в противном случае `FALSE`. В отличие от версии базового класса этот метод этот параметр не имеет значения по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE` Если перемещается области; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод аналогичен [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) , но не включает вкладку последней оставшиеся в элементе управления панели Outlook в число с плавающей запятой.  
  
##  <a name="getbuttonsfont"></a>  CMFCOutlookBar::GetButtonsFont  
 Возвращает шрифт текста на странице вкладки кнопку панели Outlook.  
  
```  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект шрифт, используемый для отображения текста в Outlook панели вкладки страницы кнопки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для получения шрифт, используемый для отображения текста на вкладках кнопка страница Outlook. Можно задать шрифт вызовом на [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).  
  
##  <a name="gettabarea"></a>  CMFCOutlookBar::GetTabArea  
 Определяет размер и положение области вкладки на панели Outlook.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectTabAreaTop`  
 При возврате из функции, содержит размер и положение области вкладок в верхней (в клиентских координатах).  
  
 [выходной] `rectTabAreaBottom`  
 При возврате из функции, содержит размер и положение области вкладок нижней (в клиентских координатах).  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить тип закрепление в целевой области. Когда платформа определяет, что пользователь перетаскивает области быть закреплено за области вкладок в целевой области, он предпринимает попытку добавления первой области в виде новой вкладки в целевой области. В противном случае он пытается закрепление первой области в соответствующие части целевой области. Платформа создает новый контейнер с помощью ползунка для размещения дополнительных закрепленной панели.  
  
 Реализация по умолчанию `GetTabArea` возвращает всю клиентскую область панели Outlook, если панель Outlook является статическим; Если панель Outlook не могут перемещаться. В противном случае он возвращает область, принимают кнопок страниц в верхней и нижней части элемента управления панель Outlook.  
  
 Переопределите этот метод в класс, производный от `CMFCOutlookBar` это поведение можно изменить.  
  
##  <a name="ismode2003"></a>  CMFCOutlookBar::IsMode2003  
 Указывает, имитирует ли поведение панели Outlook, Microsoft Office Outlook 2003.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если панель Outlook работает в режиме Microsoft Office 2003. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот режим можно включить с помощью [CMFCOutlookBar::SetMode2003](#setmode2003).  
  
##  <a name="onafteranimation"></a>  CMFCOutlookBar::OnAfterAnimation  
 Вызывается методом [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) после задания активной вкладки с помощью анимации.  
  
```  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPage`  
 Отсчитываемый от нуля индекс вкладки, которые были сделаны active.  
  
### <a name="remarks"></a>Примечания  
 Установка активной вкладки визуальный эффект зависит от того, включена ли анимация. Дополнительные сведения см. в разделе [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).  
  
##  <a name="onbeforeanimation"></a>  CMFCOutlookBar::OnBeforeAnimation  
 Вызывается методом [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) перед вкладки страницы задается в качестве активной вкладки с помощью анимации.  
  
```  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPage`  
 Отсчитываемый от нуля индекс вкладки, которые будут устанавливаться active.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` анимации должен использоваться при установке новой активной вкладки или `FALSE` при анимации должна быть отключена.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onscroll"></a>  CMFCOutlookBar::OnScroll  
 Вызывается платформой при прокрутке панели Outlook вверх или вниз.  
  
```  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDown`  
 `TRUE` Если панель Outlook прокрутку вниз, или `FALSE` , если он прокрутку вверх.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removecustompage"></a>  CMFCOutlookBar::RemoveCustomPage  
 Удаляет пользовательскую страницу вкладки панели Outlook.  
  
```  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiPage`  
 Отсчитываемый от нуля индекс страницы в родительское окно Outlook.  
  
 [in] `pTargetWnd`  
 Pointerto Outlook родительского окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользовательской страницы был удален успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию для удаления пользовательских страниц. При удалении странице его идентификатор элемента управления возвращается в пул доступных идентификаторов.  
  
 Необходимо указать указатель [класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md) объекта, в которой находится страница удаляется в настоящее время. Обратите внимание, что пользователь может перемещать отделяемые страницы между другой панели Outlook, но сведения о настраиваемой страницы находится в объекта панели Outlook, для которого был вызван [CMFCOutlookBar::CreateCustomPage](#createcustompage).  
  
 Используйте [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) для получения указателя на окно Outlook.  
  
##  <a name="setbuttonsfont"></a>  CMFCOutlookBar::SetButtonsFont  
 Задает шрифт текста, кнопок панели Outlook.  
  
```  
void SetButtonsFont(
    CFont* pFont,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pFont`  
 Указывает новый шрифт.  
  
 [in] `bRedraw`  
 Если `TRUE`, перерисовывается панели Outlook.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для задания шрифта для текста, отображаемого на кнопках страницу вкладки outlook.  
  
##  <a name="setmode2003"></a>  CMFCOutlookBar::SetMode2003  
 Указывает, имитирует ли поведение панели Outlook, Outlook 2003.  
  
```  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMode2003`  
 Значение TRUE, если включен режим Office 2003.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для включения или отключения режима Office 2003. В этом режиме панели Outlook содержит дополнительные панели инструментов с кнопкой на настройки. Поведение панели Outlook соответствует поведение панели Outlook в Microsoft Office 2003.  
  
 По умолчанию этот режим недоступен.  
  
> [!NOTE]
>  Эта функция должна вызываться перед [CMFCOutlookBar::Create](#create).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)   
 [Класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [Класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)
