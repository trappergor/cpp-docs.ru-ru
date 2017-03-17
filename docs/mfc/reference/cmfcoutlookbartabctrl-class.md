---
title: "Класс CMFCOutlookBarTabCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarTabCtrl class
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
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
ms.openlocfilehash: 16de4287a2b3a6352fb4fc560b9c8eec2ba766d1
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class
Элемент управления "вкладка", который имеет внешний вид раздела **Область переходов** в Microsoft Outlook.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Конструктор по умолчанию.|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Добавляет элемент управления Windows в виде новой вкладки панели Outlook.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Вызывается платформой для определения измерения поле редактирования, который отображается, когда пользователь переименовывает вкладки. (Переопределяет `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Вызывается средой во время операций по изменению размера для определения кнопок вкладки страницы меньше Outlook строки могут отображаться не видимые в настоящий момент.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Вызывается средой во время операций по изменению размера для определения могут отображаться дополнительные кнопки страницы вкладки панели Outlook, не видимые в настоящий момент.|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Создает элемент управления вкладки панели Outlook.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Указывает, включена ли анимация, которая происходит при переключении между вкладками active.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Указывает, может ли пользователь изменять текстовых меток для кнопок панели. (Переопределяет [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Вызывается платформой для включения кнопки, позволяющие пользователю просматривать кнопки на область панели Outlook.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Определяет области, содержащий заданной точке. (Переопределяет [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Возвращает размер границы элемента управления вкладками Outlook.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Получает размер и положение вкладки области вкладок элемента управления. (Переопределяет [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Определяет, включена ли анимация, которая происходит при переключении между вкладками active.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Определяет, является ли элемент управления вкладки панели Outlook в режиме, который эмулирует Microsoft Outlook 2003.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Определяет, является ли точка внутри области вкладки. (Переопределяет [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Определяет, является ли отключаемых вкладки. (Переопределяет [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Вызывается инфраструктурой при вставке или удалить вкладку. (Переопределяет `CMFCBaseTabCtrl::OnChangeTabs`.)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Вызывается платформой для уменьшения количества кнопок страницу вкладки, которые отображаются.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Вызывается платформой для увеличения количества кнопок страницу вкладки, которые отображаются.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Отображает **параметры области навигации** диалогового окна.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Повторно вычисляет макет внутреннего набора вкладок. (Переопределяет [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Задает активную вкладку. (Переопределяет [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Задает размер границы элемента управления вкладками Outlook.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Задает выравнивание текста метки кнопок панели Outlook.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Задает точечный рисунок, который содержит значки, которые отображаются в нижней части панели Outlook в Outlook 2003 режиме (см. [CMFCOutlookBar класса](../../mfc/reference/cmfcoutlookbar-class.md)).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать панель Outlook с поддержкой закрепления, используйте `CMFCOutlookBar` объекта для размещения панели управления "Вкладка" Outlook. Дополнительные сведения см. в разделе [CMFCOutlookBar класса](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует инициализации `CMFCOutlookBarTabCtrl` и использовать различные методы в `CMFCOutlookBarTabCtrl` класса. Пример показано, как включить редактирование на месте текстовой подписи на кнопках страницы вкладки панели Outlook, включить анимацию, включите прокрутки маркеров, которые позволяют пользователю прокручивать кнопки на область панели Outlook, устанавливается размер границы элемента управления вкладками Outlook и выравнивание текста метки на кнопках вкладку панели Outlook. Этот фрагмент кода является частью [Outlook демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo&#2;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxoutlookbartabctrl.h  
  
##  <a name="addcontrol"></a>CMFCOutlookBarTabCtrl::AddControl  
 Добавляет элемент управления Windows в виде новой вкладки панели Outlook.  
  
```  
void AddControl(
    CWnd* pWndCtrl,  
    LPCTSTR lpszName,  
    int nImageID=-1,  
    BOOL bDetachable=TRUE,  
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndCtrl`  
 Указатель на элемент управления для добавления.  
  
 [in] `lpszName`  
 Задает имя вкладки.  
  
 [in] `bDetachable`  
 Если `TRUE`, страница будет создана как отключаемых.  
  
 [in] `nImageID`  
 Индекс изображения в списке внутренней изображений для изображения для отображения в новой вкладке.  
  
 [in] `dwControlBarStyle`  
 Указывает AFX_ `CBRS_`* стиль для упакованного области закрепления.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для добавления элемента управления в виде новой страницы панель outlook.  
  
 Эта функция вызывает внутренне для [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).  
  
 Если задать `bDetachable` для `TRUE`, `AddControl` внутренне создает `CDockablePaneAdapter` объектов и создает оболочку для добавленного элемента управления. Автоматически задает класс среды выполнения окна с вкладками в класс среды выполнения `CMFCOutlookBar` и класса среды выполнения с плавающей запятой кадра, `CMultiPaneFrameWnd`.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddControl` метод `CMFCOutlookBarTabCtrl` класса. Этот фрагмент кода является частью [Outlook демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo&#3;](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 Вызывается средой во время изменения размера операций, чтобы определить, может ли отображаться меньше Outlook вкладку страницы кнопок не видимые в настоящий момент.  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если имеется более одной кнопки. в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления вкладки панели Outlook динамически добавляет или удаляет вкладки из отображения в зависимости от того, сколько места доступно. Этот метод используется платформой для помощи в этом процессе.  
  
##  <a name="canshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 Вызывается средой во время изменения размера операций, чтобы определить, может ли отображаться дополнительные кнопки страницы вкладки панели Outlook не видимые в настоящий момент.  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если имеются кнопки, которые не видны в данный момент; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления вкладки панели Outlook динамически добавляет или удаляет вкладки с экрана, в зависимости от того, сколько места доступно. Этот метод используется платформой для помощи в этом процессе.  
  
##  <a name="create"></a>CMFCOutlookBarTabCtrl::Create  
 Создает элемент управления вкладки панели Outlook.  
  
```  
virtual BOOL Create(
    const CRect& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `rect`  
 Задает начальный размер и положение в пикселях.  
  
 [in] `pParentWnd`  
 Указывает для родительского окна. Значение не должно быть равно `NULL`.  
  
 [in] `nID`  
 Идентификатор элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления был создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Как правило, создаются элементы управления вкладка панели outlook при [класса CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md) элементов управления `WM_CREATE` сообщения процесса.  
  
##  <a name="enableanimation"></a>CMFCOutlookBarTabCtrl::EnableAnimation  
 Указывает, включена ли анимация, которая происходит при переключении между вкладками active.  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Указывает, включен или отключен анимации.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для включения и отключения анимации. Когда пользователь открывает страницу вкладки, заголовок страницы слайды вверх или вниз, если включена анимация. При отключении анимации страницы немедленно становится активным.  
  
 По умолчанию включен.  
  
##  <a name="enableinplaceedit"></a>CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 Указывает, может ли пользователь изменять надписи на странице кнопок панели.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Если `TRUE`, включить редактирование на месте текстовой подписи. Если `FALSE`, отключение редактирования на месте.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для включения или отключения в оперативное изменение текстовых меток на кнопках страницы вкладки. По умолчанию отключен редактирования на месте.  
  
##  <a name="enablescrollbuttons"></a>CMFCOutlookBarTabCtrl::EnableScrollButtons  
 Вызывается платформой для включения дескрипторы прокрутки, позволяющие пользователю выполнять прокрутку кнопки на область панели Outlook.  
  
```  
void EnableScrollButtons(
    BOOL bEnable = TRUE,  
    BOOL bIsUp = TRUE,  
    BOOL bIsDown = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Определяет, отображаются ли кнопки прокрутки.  
  
 [in] `bIsUp`  
 Определяет, отображается ли верхний полосы прокрутки.  
  
 [in] `bIsDown`  
 Определяет, отображается ли нижней полосы прокрутки.  
  
### <a name="remarks"></a>Примечания  
 Позволяет отображать кнопки прокрутки. Этот метод вызывается инфраструктурой при активной вкладке восстановить кнопки прокрутки.  
  
##  <a name="getbordersize"></a>CMFCOutlookBarTabCtrl::GetBorderSize  
 Возвращает размер границы элемента управления вкладками Outlook.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер границы в пикселях.  
  
##  <a name="getvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::GetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isanimation"></a>CMFCOutlookBarTabCtrl::IsAnimation  
 Указывает, включена ли анимация, которая происходит при переключении между вкладками active.  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если включена анимация. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызов [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) функции, чтобы включить или отключить анимацию.  
  
##  <a name="ismode2003"></a>CMFCOutlookBarTabCtrl::IsMode2003  
 Определяет, является ли элемент управления вкладки панели Outlook в режиме, который эмулирует Microsoft Outlook 2003.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если Outlook панели управления "Вкладка" в Outlook 2003 режиме; в противном случае `FALSE`;  
  
### <a name="remarks"></a>Примечания  
 Это значение задается [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).  
  
##  <a name="onshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 Вызывается платформой для уменьшения количества кнопок страницу вкладки, которые отображаются.  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод изменяет число кнопок вкладку отображения страницы, при изменении размера элемента управления.  
  
##  <a name="onshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 Вызывается платформой для увеличения количества кнопок страницу вкладки, которые отображаются.  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод измените число кнопок страницу вкладки, которые отображаются, если размеры элемента управления.  
  
##  <a name="onshowoptions"></a>CMFCOutlookBarTabCtrl::OnShowOptions  
 Отображает **параметры области навигации** диалоговое окно.  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>Примечания  
 **Параметры области навигации** диалоговое окно позволяет пользователю select, в которой должны отображаться вкладка страницы кнопки и порядок, в котором они отображаются.  
  
 Этот метод вызывается инфраструктурой при выборе **параметры области навигации** элемент меню из меню настройки элемента управления.  
  
##  <a name="setactivetab"></a>CMFCOutlookBarTabCtrl::SetActiveTab  
 Задает активную вкладку. Активную вкладку является тот, который был открыт, отображается ее содержимое.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки для открытия.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если за указанной вкладкой было установлено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Визуальный эффект настройки активной вкладке зависит от того, включена ли анимация. Дополнительные сведения см. в разделе [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).  
  
##  <a name="setbordersize"></a>CMFCOutlookBarTabCtrl::SetBorderSize  
 Задает размер границы элемента управления вкладками Outlook.  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nBorderSize`  
 Указывает новый размер границы в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Задает новый размер границы и повторно вычисляет макет окна outlook.  
  
##  <a name="setpagebuttontextalign"></a>CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Задает выравнивание текста метки кнопок панели Outlook.  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiAlign`  
 Задает выравнивание текста.  
  
 [in] `bRedraw`  
 Если `TRUE`, в окне outlook перерисовывается.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для изменения выравнивания текста для кнопки на странице.  
  
 `uiAlign`может принимать одно из следующих значений:  
  
|Константа|Значение|  
|--------------|-------------|  
|TA_LEFT|Выравнивание по левому краю|  
|TA_CENTER|Выравнивание по центру|  
|TA_RIGHT|Выравнивание по правому краю|  
  
 Значение по умолчанию — TA_CENTER.  
  
##  <a name="settoolbarimagelist"></a>CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Задает точечный рисунок, содержащий значки, которые отображаются в нижней части панели Outlook в Outlook 2003 режиме.  
  
```  
BOOL SetToolbarImageList(
    UINT uiID,  
    int cx,  
    COLORREF clrTransp=RGB(255, 0, 255));
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiID`  
 Указывает идентификатор ресурса изображения для загрузки.  
  
 [in] `cx`  
 Задает ширину изображения в списке изображений в пикселях.  
  
 [in] `clrTransp`  
 Значение RGB определяет прозрачный цвет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` в случае успешного выполнения; в противном случае возвращает `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для присоединения списка изображений, отображаемых изображений будет на кнопки панели инструментов в режиме Microsoft Office 2003. Индексы образа должна соответствовать страницы индексов.  
  
 Этот метод не должен вызываться не в Microsoft Office 2003 режиме. Дополнительные сведения см. в разделе [CMFCOutlookBar класса](../../mfc/reference/cmfcoutlookbar-class.md).  
  
##  <a name="setvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::SetVisiblePageButtons  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetVisiblePageButtons(int nVisiblePageButtons);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nVisiblePageButtons`  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)   
 [Класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

