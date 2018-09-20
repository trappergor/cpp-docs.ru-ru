---
title: Класс CMFCOutlookBar | Документация Майкрософт
ms.custom: ''
ms.date: 06/25/2018
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
ms.openlocfilehash: 0597cc6dd2c52792f583d23a45bbafe8bc996ffd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374507"
---
# <a name="cmfcoutlookbar-class"></a>Класс CMFCOutlookBar

Область со вкладками, которая имеет внешний вид области **Область переходов** в Microsoft Outlook 2000 или Outlook 2003. `CMFCOutlookBar` Объект содержит [класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md) объекта и ряд вкладок. Вкладки могут быть [класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) объектов или `CWnd`-объекты, производные от. Пользователю панель Outlook отображается как последовательность кнопок и область отображения. Когда пользователь нажимает кнопку, отображается соответствующая область элемента управления или кнопки.

## <a name="syntax"></a>Синтаксис

```cpp
class CMFCOutlookBar : public CBaseTabbedPane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCOutlookBar::CMFCOutlookBar`|Конструктор по умолчанию.|
|`CMFCOutlookBar::~CMFCOutlookBar`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Указывает, можно ли уничтожить пустой области с вкладками. (Переопределяет [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Определяет, ли другую панель можно закрепить область панели Outlook. (Переопределяет CDockablePane::CanAcceptPane).|
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Определяет, отображает ли заголовок для области с вкладками тот же текст в качестве активной вкладки. (Переопределяет [CBaseTabbedPane::CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname).)|
|[CMFCOutlookBar::Create](#create)|Создает элемент управления панели Outlook.|
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Создание настраиваемой вкладки панели Outlook.|
|`CMFCOutlookBar::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCOutlookBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, является ли пользователь можно закрепить на панели элементов управления на внешней границе панели Outlook.|
|[CMFCOutlookBar::FloatTab](#floattab)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке. (Переопределяет [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Возвращает шрифт для текста на кнопках панели Outlook.|
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Возвращает размер и положение области вкладки на панели Outlook. (Переопределяет [CBaseTabbedPane::GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|
|`CMFCOutlookBar::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Определяет, ли поведение панели Outlook имитирует, Microsoft Office Outlook 2003 (см. в разделе "Примечания").|
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Вызывается средой [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) после задания активной вкладки с помощью анимации.|
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Вызывается средой [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) перед вкладку страница задана в качестве активной вкладки с помощью анимации.|
|[CMFCOutlookBar::OnScroll](#onscroll)|Вызывается платформой при прокрутке панели Outlook вверх или вниз.|
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Удаляет вкладку на настраиваемой панели Outlook.|
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Задает шрифт текста на кнопках панели Outlook.|
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Указывает ли поведение панели Outlook имитирует, Outlook 2003 (см. в разделе "Примечания").|

## <a name="remarks"></a>Примечания

Пример того, панель Outlook, см. в разделе [образце OutlookDemo: приложение MFC OutlookDemo](../../visual-cpp-samples.md).

## <a name="implementing-the-outlook-bar"></a>Реализация панели Outlook

Для использования элемента управления `CMFCOutlookBar` в своем приложении выполните следующие действия:

1. Внедрите объект `CMFCOutlookBar` в класс окна главного фрейма.

    ```cpp
    class CMainFrame : public CMDIFrameWnd
    {
        // ...
        CMFCOutlookBar m_wndOutlookBar;
        CMFCOutlookBarPane m_wndOutlookPane;
        // ...
    };
    ```

1. При обработке сообщений WM_CREATE в главном фрейме, вызовите [CMFCOutlookBar::Create](#create) метод для создания панели управления "Вкладка" Outlook.

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. Получить указатель на базовый `CMFCOutlookBarTabCtrl` с помощью [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. Создание [класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) объект для каждой вкладки, которая содержит кнопки.

    ```cpp
    m_wndOutlookPane.Create(&m_wndOutlookBar,
        AFX_DEFAULT_TOOLBAR_STYLE,
        ID_OUTLOOK_PANE_GENERAL,
        AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);

    // make the Outlook pane detachable (enable docking)
    m_wndOutlookPane.EnableDocking(CBRS_ALIGN_ANY);

    // add buttons
    m_wndOutlookPane.AddButton(theApp.LoadIcon (IDR_MAINFRAME),
        "About",
        ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON),
        "Open",
        ID_FILE_OPEN);
    ```

1. Вызовите [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) для добавления каждой новой вкладке. Задайте *bDetachable* параметра значение false, чтобы сделать страницу неотделяемые. Также можно использовать [CMFCOutlookBarTabCtrl::AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) добавить отделяемые страницы.

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. Для добавления `CWnd`-производного элемента управления (например, [класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)) на отдельной вкладке Создание элемента управления и вызвать [CMFCOutlookBarTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) Чтобы добавить его на панель Outlook.

> [!NOTE]
>  Следует использовать уникальные идентификаторы элементов управления для каждого [класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) объекта и для каждого `CWnd`-объект, производный от.

Чтобы динамически добавить или удалить новых страниц во время выполнения, используйте [CMFCOutlookBar::CreateCustomPage](#createcustompage) и [CMFCOutlookBar::RemoveCustomPage](#removecustompage).

## <a name="outlook-2003-mode"></a>Outlook 2003 режиме

В Outlook 2003 режиме кнопок вкладки располагаются в нижней части область панели Outlook. Если имеется достаточно места для отображения кнопок, они будут показаны как значки в стиле панели инструментов области в нижней части области.

Используйте [CMFCOutlookBar::SetMode2003](#setmode2003) для включения режима Outlook 2003. Используйте [CMFCOutlookBarTabCtrl::SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) присвоить точечного рисунка, который содержит значки, которые отображаются в нижней части панели Outlook. Значки в битовой карте должны быть упорядочены по клавише tab.

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

Указывает, можно ли уничтожить пустой области с вкладками.

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если пустой области с вкладками можно уничтожить; в противном случае — значение FALSE. Реализация по умолчанию всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Если не может быть удалено пустой области с вкладками, framework скрывает его вместо этого.

##  <a name="canacceptpane"></a>  CMFCOutlookBar::CanAcceptPane

Определяет, ли другую панель можно закрепить область панели Outlook.

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
[in] Указатель на другую панель, расположенной на эту панель.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если другой области можно прикреплять к область панели Outlook; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если строка находится в режиме Outlook 2003, закрепление Outlook не поддерживается, поэтому возвращаемое значение равно FALSE.

Если *pBar* параметр имеет значение NULL, этот метод возвращает значение FALSE.

В противном случае этот метод ведет себя как базовый метод [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane), за исключением того, что даже если закрепление не включена, панель Outlook можно включить другую панель Outlook можно закреплять над ней.

##  <a name="cansetcaptiontexttotabname"></a>  CMFCOutlookBar::CanSetCaptionTextToTabName

Определяет, отображает ли заголовок для области с вкладками тот же текст в качестве активной вкладки.

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если панели заголовка окна Outlook автоматически присваивается текста активной вкладки; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Используйте [CBaseTabbedPane::EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) для включения или отключения этой функции.

В Outlook 2003 режиме этот параметр всегда включен.

##  <a name="create"></a>  CMFCOutlookBar::Create

Создает элемент управления панели Outlook.

```cpp
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

*lpszCaption*<br/>
[in] Задает заголовок окна.

*pParentWnd*<br/>
[in] Задает указатель на родительское окно. Он не должен иметь значение NULL.

*Rect*<br/>
[in] Задает размер и положение в точках панели outlook.

*nID*<br/>
[in] Указывает идентификатор элемента управления. Должно отличаться от других идентификаторов, используемых в приложении элементов управления.

*dwStyle*<br/>
[in] Задает стиль панели требуемого элемента управления. Возможные значения см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*dwControlBarStyle*<br/>
[in] Указывает специальные стили, определенные в библиотеке.

*pContext*<br/>
[in] Создайте контекст.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

При создании `CMFCOutlookBar` объекта в два этапа. Сначала вызовите конструктор, а затем вызвать `Create`, который создает элемент управления панели outlook и присоединяет его к `CMFCOutlookBar` объекта.

См. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) список Доступные стили определяемое библиотекой указываемых по *dwControlBarStyle*.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `Create` метод `CMFCOutlookBar` класса. Этот фрагмент кода является частью [пример Outlook с несколькими представлениями](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

##  <a name="createcustompage"></a>  CMFCOutlookBar::CreateCustomPage

Создание настраиваемой вкладки панели Outlook.

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszPageName*<br/>
[in] Подпись.

*bActivatePage*<br/>
[in] Значение TRUE, если страница становится активной во время создания.

*dwEnabledDocking*<br/>
[in] Сочетание CBRS_ALIGN_ флагов, указывающее, включено закрепление сторон при отсоединении страницы.

*bEnableTextLabels*<br/>
[in] Значение TRUE, если текстовые метки включены для кнопок, которые находятся на странице.

### <a name="return-value"></a>Возвращаемое значение

Указатель на только что созданную страницу, или значение NULL, если не удалось создать.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы пользователи могли создавать пользовательские страницы панели Outlook. Можно создать до 100 страниц в приложения. Элемент управления страницы, запустите идентификаторы в число 0xf000 не. Создание завершается сбоем, если общее число настраиваемых страниц панели Outlook превышает 100.

Используйте [CMFCOutlookBar::RemoveCustomPage](#removecustompage) удалить настраиваемые страницы.

##  <a name="doesallowdyninsertbefore"></a>  CMFCOutlookBar::DoesAllowDynInsertBefore

Указывает, можно ли пользователь Закрепить панель на внешней границе панели Outlook.

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

Реализация по умолчанию возвращает значение FALSE.

### <a name="remarks"></a>Примечания

Платформа вызывает `DoesAllowDynInsertBefore` метод при поиске расположения Закрепить панель динамического. Если функция возвращает значение FALSE, платформа не поддерживает закрепление панели любого динамического во внешние края области.

Как правило создается панель Outlook как статический элемент управления не с плавающей запятой. Можно переопределить эту функцию в производном классе и возвращает значение TRUE, чтобы изменить это поведение.

> [!NOTE]
>  Так как динамические области проверить состояние закрепленных панелей статические, если закрепления, должны закрепляться динамической области после статические области, когда это возможно.

##  <a name="floattab"></a>  CMFCOutlookBar::FloatTab

Преобразует панель.

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
[in] Указатель на панель, число с плавающей запятой.

*nTabID*<br/>
[in] Отсчитываемый от нуля индекс вкладки, число с плавающей запятой.

*dockMethod*<br/>
[in] Задает метод, с помощью панели float.  Дополнительные сведения см. в разделе [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).

*bHide*<br/>
[in] Значение TRUE, чтобы скрыть область перед с плавающей запятой; в противном случае — значение FALSE. В отличие от версии базового класса этого метода этот параметр не имеет значения по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если оставить плавающим области; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод аналогичен [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) за исключением того, что не позволяет последняя вкладка оставшиеся в элементе управления панели Outlook число с плавающей запятой.

##  <a name="getbuttonsfont"></a>  CMFCOutlookBar::GetButtonsFont

Возвращает шрифт текста на странице вкладки кнопки панели Outlook.

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект шрифта, используемый для отображения текста в Outlook панели вкладки страницы кнопку.

### <a name="remarks"></a>Примечания

Эта функция используется для получения шрифт, используемый для отображения текста кнопки вкладки Outlook. Шрифт можно задать путем вызова для [CMFCOutlookBar::SetButtonsFont](#setbuttonsfont).

##  <a name="gettabarea"></a>  CMFCOutlookBar::GetTabArea

Определяет размер и положение области вкладки на панели Outlook.

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Параметры

*rectTabAreaTop*<br/>
[out] Содержит размер и положение области вкладок верхнего (в координатах клиентской области окна), при возврате функции.

*rectTabAreaBottom*<br/>
[out] Содержит размер и положение области вкладок нижней (в координатах клиентской области окна), при возврате функции.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод, чтобы определить тип закрепление в нужной области. Когда платформа определяет, что пользователь перетаскивает области быть закреплено над областью панели вкладки целевой области, он пытается добавить первой области как новая вкладка целевой области. В противном случае он пытается закрепление области первой в соответствующие части целевой области. Платформа создает новый контейнер с помощью ползунка для размещения дополнительных закрепленной панели.

Реализация по умолчанию `GetTabArea` возвращает всю клиентскую область панели Outlook, если панели Outlook является статическим; это, если не могут перемещаться панели Outlook. В противном случае он возвращает область, принимать кнопок страниц в верхней и нижней части элемента управления панели Outlook.

Переопределите этот метод в класс, производный от `CMFCOutlookBar` это поведение можно изменить.

##  <a name="ismode2003"></a>  CMFCOutlookBar::IsMode2003

Указывает ли поведение панели Outlook имитирует, Microsoft Office Outlook 2003.

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если панели Outlook работает в режиме Microsoft Office 2003; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот режим можно включить с помощью [CMFCOutlookBar::SetMode2003](#setmode2003).

##  <a name="onafteranimation"></a>  CMFCOutlookBar::OnAfterAnimation

Вызывается средой [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) после задания активной вкладки с помощью анимации.

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>Параметры

*nPage*<br/>
[in] Отсчитываемый от нуля индекс страницы вкладки, которые были сделаны active.

### <a name="remarks"></a>Примечания

Визуальный эффект настройки активной вкладкой зависит от того, включена ли анимация. Дополнительные сведения см. в разделе [CMFCOutlookBarTabCtrl::EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).

##  <a name="onbeforeanimation"></a>  CMFCOutlookBar::OnBeforeAnimation

Вызывается средой [CMFCOutlookBarTabCtrl::SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) перед вкладку страница задана в качестве активной вкладки с помощью анимации.

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>Параметры

*nPage*<br/>
[in] Отсчитываемый от нуля индекс страницы вкладки, которая должна задаваться active.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если анимация должна использоваться при установке новой активной вкладкой, или значение FALSE, если анимация должна быть отключена.

### <a name="remarks"></a>Примечания

##  <a name="onscroll"></a>  CMFCOutlookBar::OnScroll

Вызывается платформой при прокрутке панели Outlook вверх или вниз.

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>Параметры

*bDown*<br/>
[in] Значение TRUE, если панели Outlook прокрутите вниз, или значение FALSE, если он прокрутки вверх.

### <a name="remarks"></a>Примечания

##  <a name="removecustompage"></a>  CMFCOutlookBar::RemoveCustomPage

Удаляет пользовательские вкладки панели Outlook.

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>Параметры

*uiPage*<br/>
[in] Отсчитываемый от нуля индекс страницы в родительском окне Outlook.

*pTargetWnd*<br/>
[in] Pointerto Outlook родительского окна.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если пользовательская страница удалена успешно. в противном случае 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для удаления пользовательских страниц. При удалении страницы его идентификатор элемента управления возвращается в пул доступных идентификаторов.

Необходимо предоставить указатель на [класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md) объекта, в которой находится страницы, чтобы удалить сейчас. Обратите внимание, что пользователь может перемещать отделяемые страниц между разные столбцы Outlook, но сведения о пользовательской страницы находится в объекте панели Outlook, для которого был вызван [CMFCOutlookBar::CreateCustomPage](#createcustompage).

Используйте [CBaseTabbedPane::GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) получить указатель на окно Outlook.

##  <a name="setbuttonsfont"></a>  CMFCOutlookBar::SetButtonsFont

Задает шрифт текста на кнопках панели Outlook.

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*pFont*<br/>
[in] Указывает новый шрифт.

*bRedraw*<br/>
[in] Если значение равно TRUE, перерисовывается панели Outlook.

### <a name="remarks"></a>Примечания

Этот метод позволяет задать шрифт для текста, отображаемого на кнопках страницы вкладки outlook.

##  <a name="setmode2003"></a>  CMFCOutlookBar::SetMode2003

Указывает ли поведение панели Outlook имитирует, Outlook 2003.

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>Параметры

*bMode2003*<br/>
[in] Значение TRUE, если включен режим Office 2003.

### <a name="remarks"></a>Примечания

Эта функция используется для включения или отключения режима Office 2003. В этом режиме панели Outlook содержит дополнительные панели инструментов с кнопкой "настройки". Поведение панели Outlook соответствует поведению панели Outlook в Microsoft Office 2003.

По умолчанию этот режим отключен.

> [!NOTE]
>  Эта функция должна вызываться перед [CMFCOutlookBar::Create](#create).

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[Класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[Класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)
