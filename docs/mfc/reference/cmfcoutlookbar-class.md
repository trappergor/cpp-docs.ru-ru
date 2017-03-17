---
title: "Класс CMFCOutlookBar | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCOutlookBar class
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
caps.latest.revision: 34
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ff58cf786e4979d64aa2b5d7ad4d1a32b96bec3d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbar-class"></a>Класс CMFCOutlookBar
Область со вкладками, которая имеет внешний вид области **Область переходов** в Microsoft Outlook 2000 или Outlook 2003. `CMFCOutlookBar` Объект содержит [CMFCOutlookBarTabCtrl класс](../../mfc/reference/cmfcoutlookbartabctrl-class.md) объекта и ряд вкладок. Вкладки могут быть [класса CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) объектов или `CWnd`-производных объектов. Пользователю панель Outlook отображается как последовательность кнопок и область отображения. Когда пользователь нажимает кнопку, отображается соответствующая область элемента управления или кнопки.  
  
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
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Указывает, можно ли удалить пустая область с вкладками. (Переопределяет [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|  
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Определяет, является ли другую панель можно закрепить область панели Outlook. (Переопределяет CDockablePane::CanAcceptPane).|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Определяет, отображать ли заголовок панели с вкладками тот же текст в активную вкладку. (Переопределяет [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|  
|[CMFCOutlookBar::Create](#create)|Создает элемент управления панели Outlook.|  
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Создание настраиваемой вкладки панели Outlook.|  
|`CMFCOutlookBar::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, может ли пользователь Закрепить панель элементов управления на внешней границе панели Outlook.|  
|[CMFCOutlookBar::FloatTab](#floattab)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке. (Переопределяет [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|  
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Возвращает шрифт для текста на кнопках панели Outlook.|  
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Возвращает размер и положение областей вкладку на панели Outlook. (Переопределяет [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|  
|`CMFCOutlookBar::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Определяет, имитирует ли поведение панели Outlook, Microsoft Office Outlook 2003 (см. примечания).|  
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Вызывается методом [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) после активной вкладки с помощью анимации.|  
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Вызывается методом [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) перед вкладки страницы задается как активной вкладки, с помощью анимации.|  
|[CMFCOutlookBar::OnScroll](#onscroll)|Вызывается инфраструктурой при прокрутке вверх или вниз на панели Outlook.|  
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Удаляет пользовательскую вкладку панели Outlook.|  
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Задает шрифт для текста на кнопках панели Outlook.|  
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Указывает, копирует ли поведение панели Outlook, Outlook 2003 (см. примечания).|  
  
## <a name="remarks"></a>Примечания  
 Пример панели Outlook, см. [образце OutlookDemo: приложение MFC OutlookDemo](../../visual-cpp-samples.md).  
  
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
2.  При обработке `WM_CREATE` сообщения в главном фрейме, вызов [CMFCOutlookBar::Create](#create) метод для создания панели управления "Вкладка" Outlook.  
  
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
4.  Создание [CMFCOutlookBarPane класса](../../mfc/reference/cmfcoutlookbarpane-class.md) объект для каждой вкладки, содержащую кнопки.  
  
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
5.  Вызов [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) для добавления каждой новой вкладке. Задайте `bDetachable` параметр `FALSE` вносить не отключаемых страницы. Или используйте [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) добавления отключаемых страниц.  
  
 ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1,
    TRUE);

 ```  
6.  Добавление `CWnd`-производного элемента управления (например, [класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)) в виде вкладки, создание элемента управления и вызвать [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) Добавление на панель Outlook.  
  
> [!NOTE]
>  Следует использовать уникальные идентификаторы элементов управления для каждого [класса CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) объекта и для каждого `CWnd`-производный объект.  
  
 Чтобы динамически добавлять или удалять новые страницы во время выполнения, используйте [CMFCOutlookBar::CreateCustomPage](#createcustompage) и [CMFCOutlookBar::RemoveCustomPage](#removecustompage).  
  
## <a name="outlook-2003-mode"></a>Outlook 2003 режиме  
 В Outlook 2003 режиме кнопки вкладки расположены в нижней части область панели Outlook. Не достаточно места для отображения кнопок, отображаемых в виде значков в области в нижней части панели инструментов в стиле.  
  
 Используйте [CMFCOutlookBar::SetMode2003](#setmode2003) для включения режима Outlook 2003. Используйте [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) присвоить точечного рисунка, содержащий значки, которые отображаются в нижней части панели Outlook. Значки в битовой карте должны быть упорядочены по клавише tab.  
  
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
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCOutlookBar::AllowDestroyEmptyTabbedPane  
 Указывает, можно ли удалить пустая область с вкладками.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если пустая область с вкладками можно быть уничтожено; в противном случае — `FALSE`. Реализация по умолчанию всегда возвращает `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Если не может быть уничтожен пустая область с вкладками, платформа скрывает его вместо.  
  
##  <a name="canacceptpane"></a>CMFCOutlookBar::CanAcceptPane  
 Определяет, является ли другую панель можно закрепить область панели Outlook.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на другую панель, которая присоединяется к этой области.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если другой области можно закрепить область панели Outlook; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если панель Outlook в Outlook 2003 режиме, закрепление не поддерживаются, поэтому возвращается значение `FALSE`.  
  
 Если `pBar` параметр `NULL`, этот метод возвращает `FALSE`.  
  
 В противном случае, этот метод ведет себя как базовый метод [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane), за исключением того, что даже если закрепление не включен, панель Outlook можно включить другую панель Outlook можно закреплять на него.  
  
##  <a name="cansetcaptiontexttotabname"></a>CMFCOutlookBar::CanSetCaptionTextToTabName  
 Определяет, отображать ли заголовок панели с вкладками тот же текст в активную вкладку.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если панели заголовка окна Outlook автоматически присваивается текст активной вкладке; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) для включения или отключения этой функции.  
  
 В Outlook 2003 режиме этот параметр всегда включен.  
  
##  <a name="create"></a>CMFCOutlookBar::Create  
 Создает элемент управления панели Outlook.  
  
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
 Задает указатель на родительское окно. Он не должен иметь значение NULL.  
  
 [in] `rect`  
 Задает размер и положение в пикселях на панели outlook.  
  
 [in] `nID`  
 Указывает идентификатор элемента управления. Должно отличаться от других элементов управления идентификаторы, используемые в приложении.  
  
 [in] `dwStyle`  
 Указывает стиль панели нужный элемент управления. Возможные значения см. в разделе [стили окна](../../mfc/reference/window-styles.md).  
  
 [in] `dwControlBarStyle`  
 Указывает специальные стили, определенные в библиотеке.  
  
 [in] `pContext`  
 Создание контекста.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если метод выполнен успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CMFCOutlookBar` объекта в два этапа. Сначала вызовите конструктор, а затем вызвать `Create`, который создает элемент управления панели outlook и присоединяет его к `CMFCOutlookBar` объекта.  
  
 В разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) список доступных стилей определенные библиотеки по `dwControlBarStyle`.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `Create` метод `CMFCOutlookBar` класса. Этот фрагмент кода является частью [нескольких представлений Outlook образец](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews&#1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews&#2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]  
  
##  <a name="createcustompage"></a>CMFCOutlookBar::CreateCustomPage  
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
 Если `TRUE`, страница становится активной после создания.  
  
 [in] `dwEnabledDocking`  
 Сочетание флагов CBRS_ALIGN_, указывающее, включено закрепление сторон при отсоединении страницы.  
  
 [in] `bEnableTextLabels`  
 Если `TRUE`, поддержкой текстовые метки кнопок, которые находятся на странице.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на только что созданный страницы или `NULL` при создании произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы разрешить пользователям создавать пользовательские страницы панели Outlook. Можно создать до 100 страниц в приложении. Страница управления идентификаторами начиная число 0xf000 не. Создание завершается сбоем, если общее число настраиваемых страниц панели Outlook превышает 100.  
  
 Используйте [CMFCOutlookBar::RemoveCustomPage](#removecustompage) для удаления пользовательских страниц.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCOutlookBar::DoesAllowDynInsertBefore  
 Указывает, может ли пользователь Закрепление панели на внешней границе панели Outlook.  
  
```  
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация по умолчанию возвращает значение `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает функцию `DoesAllowDynInsertBefore` при поиске расположения закрепить область динамического метода. Если функция возвращает `FALSE`, платформа не допускает закрепление любой динамической панели во внешние края панели.  
  
 Как правило создается панель Outlook как статический элемент управления не с плавающей запятой. Можно переопределить эту функцию в производном классе и вернуть `TRUE` для изменения этого поведения.  
  
> [!NOTE]
>  Поскольку динамические области проверки состояния закрепленных панелей статического при закрепления, должны закрепляться динамических панелей после статические области, по возможности.  
  
##  <a name="floattab"></a>CMFCOutlookBar::FloatTab  
 Смещает область.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pBar`  
 Указатель на область с плавающей запятой.  
  
 [in] `nTabID`  
 Отсчитываемый от нуля индекс вкладки с плавающей запятой.  
  
 [in] `dockMethod`  
 Указывает метод, с помощью панели с плавающей запятой.  Дополнительные сведения см. в разделе [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).  
  
 [in] `bHide`  
 `TRUE`Чтобы скрыть область перед с плавающей запятой; в противном случае — `FALSE`. В отличие от версии базового класса этого метода этот параметр не имеет значения по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если оставить плавающим области; в противном случае — `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод аналогичен [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) , но не включает вкладку последней оставшиеся в элементе управления панели Outlook с плавающей запятой.  
  
##  <a name="getbuttonsfont"></a>CMFCOutlookBar::GetButtonsFont  
 Возвращает шрифт текста на странице вкладки кнопка панели Outlook.  
  
```  
CFont* GetButtonsFont() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект шрифт, используемый для отображения текста в Outlook панели вкладки кнопка.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для получения шрифт, используемый для отображения текста на вкладки кнопки Outlook. Можно задать шрифт, вызывая [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).  
  
##  <a name="gettabarea"></a>CMFCOutlookBar::GetTabArea  
 Определяет размер и положение областей вкладку на панели Outlook.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `rectTabAreaTop`  
 Содержит размер и положение (в координатах клиента) вкладку верхней области при возврате из функции.  
  
 [выходной] `rectTabAreaBottom`  
 Когда функция возвращает значение, содержит размер и положение (в координатах клиента) в нижней области вкладки.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, чтобы определить тип закрепление в целевой области. Если платформа определяет, что пользователь перетаскивает области, чтобы закрепить в области вкладки целевой области, он пытается добавить первой области в виде новой вкладки целевой области. В противном случае он пытается закрепление первой области в соответствующие части целевой области. Платформа создает новый контейнер с помощью ползунка для размещения дополнительных закрепленной панели.  
  
 Реализация по умолчанию `GetTabArea` возвращает всей клиентской области панели Outlook, если на панели Outlook является статическим; это, если не могут перемещаться панели Outlook. В противном случае — возвращает область, принимать страницы кнопки в верхней и нижней части элемента управления панели Outlook.  
  
 Переопределите этот метод в класс, производный от `CMFCOutlookBar` для изменения этого поведения.  
  
##  <a name="ismode2003"></a>CMFCOutlookBar::IsMode2003  
 Указывает, копирует ли поведение панели Outlook, Microsoft Office Outlook 2003.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если на панели Outlook работает в режиме Microsoft Office 2003; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот режим можно включить с помощью [CMFCOutlookBar::SetMode2003](#setmode2003).  
  
##  <a name="onafteranimation"></a>CMFCOutlookBar::OnAfterAnimation  
 Вызывается методом [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) после активной вкладки с помощью анимации.  
  
```  
virtual void OnAfterAnimation(int nPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPage`  
 Отсчитываемый от нуля индекс страницы вкладки, которые были сделаны active.  
  
### <a name="remarks"></a>Примечания  
 Визуальный эффект настройки активной вкладке зависит от того, включена ли анимация. Дополнительные сведения см. в разделе [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).  
  
##  <a name="onbeforeanimation"></a>CMFCOutlookBar::OnBeforeAnimation  
 Вызывается методом [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) перед вкладки страницы задается как активной вкладки, с помощью анимации.  
  
```  
virtual BOOL OnBeforeAnimation(int nPage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nPage`  
 Отсчитываемый от нуля индекс страницы вкладки, которые будут устанавливаться active.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` если анимация должна использоваться при установке новой активной вкладки или `FALSE` если анимация должна быть отключена.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="onscroll"></a>CMFCOutlookBar::OnScroll  
 Вызывается инфраструктурой при прокрутке вверх или вниз на панели Outlook.  
  
```  
virtual void OnScroll(BOOL bDown);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bDown`  
 `TRUE`При прокрутке панели Outlook, или `FALSE` , если он прокрутку вверх.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="removecustompage"></a>CMFCOutlookBar::RemoveCustomPage  
 Удаляет пользовательские вкладки панели Outlook.  
  
```  
BOOL RemoveCustomPage(
    UINT uiPage,  
    CMFCOutlookBarTabCtrl* pTargetWnd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiPage`  
 Отсчитываемый от нуля индекс страницы в родительском окне Outlook.  
  
 [in] `pTargetWnd`  
 Pointerto родительского окна Outlook.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если пользовательская страница удалена успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для удаления пользовательских страниц. Когда страница удаляется его идентификатор элемента управления возвращается в пул доступных идентификаторов.  
  
 Необходимо предоставить указатель [CMFCOutlookBarTabCtrl класс](../../mfc/reference/cmfcoutlookbartabctrl-class.md) объекта, в котором находится страница удаляется в настоящее время. Обратите внимание, что пользователь может перемещаться по отключаемых страниц различные панели Outlook, но сведения о пользовательской страницы находится в объект панели Outlook, для которого вызван [CMFCOutlookBar::CreateCustomPage](#createcustompage).  
  
 Используйте [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) может получить указатель на окно Outlook.  
  
##  <a name="setbuttonsfont"></a>CMFCOutlookBar::SetButtonsFont  
 Задает шрифт для текста на кнопках панели Outlook.  
  
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
 Используйте этот метод для задания шрифта для текста, отображаемого в outlook кнопок страницы вкладки.  
  
##  <a name="setmode2003"></a>CMFCOutlookBar::SetMode2003  
 Указывает, копирует ли поведение панели Outlook, Outlook 2003.  
  
```  
void SetMode2003(BOOL bMode2003=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bMode2003`  
 Значение TRUE, если включен режим Office 2003.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для включения или отключения режима Office 2003. В этом режиме панели Outlook содержит дополнительных инструментов, с помощью кнопки настройки. Поведение панели Outlook соответствует поведению панели Outlook в Microsoft Office 2003.  
  
 По умолчанию этот режим отключен.  
  
> [!NOTE]
>  Эта функция должна вызываться перед [CMFCOutlookBar::Create](#create).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)   
 [Класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [Класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

