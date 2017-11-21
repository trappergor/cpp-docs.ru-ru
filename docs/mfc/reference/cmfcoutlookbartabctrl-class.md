---
title: "Класс CMFCOutlookBarTabCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CMFCOutlookBarTabCtrl [MFC], AddControl
- CMFCOutlookBarTabCtrl [MFC], CanShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], CanShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], Create
- CMFCOutlookBarTabCtrl [MFC], EnableAnimation
- CMFCOutlookBarTabCtrl [MFC], EnableInPlaceEdit
- CMFCOutlookBarTabCtrl [MFC], EnableScrollButtons
- CMFCOutlookBarTabCtrl [MFC], GetBorderSize
- CMFCOutlookBarTabCtrl [MFC], GetVisiblePageButtons
- CMFCOutlookBarTabCtrl [MFC], IsAnimation
- CMFCOutlookBarTabCtrl [MFC], IsMode2003
- CMFCOutlookBarTabCtrl [MFC], OnShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowOptions
- CMFCOutlookBarTabCtrl [MFC], SetActiveTab
- CMFCOutlookBarTabCtrl [MFC], SetBorderSize
- CMFCOutlookBarTabCtrl [MFC], SetPageButtonTextAlign
- CMFCOutlookBarTabCtrl [MFC], SetToolbarImageList
- CMFCOutlookBarTabCtrl [MFC], SetVisiblePageButtons
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 19a1c373bc982828bfa26f89955bce684fb7e68c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class
Элемент управления "вкладка", который имеет внешний вид раздела **Область переходов** в Microsoft Outlook.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
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
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Вызывается платформой для определения измерения поле ввода, который появляется, если пользователь переименовывает вкладки. (Переопределяет `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Вызывается средой во время операций по изменению размера для определения кнопок вкладки страницы меньше Outlook строки могут отображаться не видимы.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Вызывается средой во время операций по изменению размера ли дополнительные кнопки страницы вкладки панели Outlook могут отображаться не видимы.|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Создает элемент управления вкладки панели Outlook.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Указывает, включена ли анимация, которая происходит во время переключения между активных вкладок.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Указывает, может ли пользователь изменить текстовые метки на панели кнопок. (Переопределяет [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Вызывается платформой для включения кнопки, позволяющие пользователю просматривать кнопок на область панели Outlook.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Определяет область, содержащую указанную точку. (Переопределяет [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Возвращает размер границы элемента управления tab Outlook.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Извлекает размер и положение области вкладок элемента управления tab. (Переопределяет [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Определяет, включена ли анимация, которая происходит во время переключения между активных вкладок.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Определяет, является ли элемент управления вкладки панели Outlook в режиме, который эмулирует Microsoft Outlook 2003.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Определяет, является ли точка в области вкладок. (Переопределяет [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Определяет, является ли вкладка отделяемой. (Переопределяет [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Вызывается платформой при подключении или отключении вкладки. (Переопределяет `CMFCBaseTabCtrl::OnChangeTabs`.)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Вызывается платформой, чтобы уменьшить число кнопок вкладки страницы, которые видны.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Вызывается платформой для увеличения числа кнопок вкладки страницы, которые видны.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Отображает **параметры области переходов** диалогового окна.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Повторно вычисляет внутренний макет элемента управления tab. (Переопределяет [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Задает активной вкладки. (Переопределяет [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Задает размер границ элемента управления tab Outlook.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Задает выравнивание текста меток для кнопок панели Outlook.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Задает точечного рисунка, который содержит значки, которые отображаются в нижней части панели Outlook в режиме Outlook 2003 (см. [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать панель Outlook с поддержкой закрепления, используйте `CMFCOutlookBar` объекта для размещения панели управления "Вкладка" Outlook. Дополнительные сведения см. в разделе [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как инициализировать `CMFCOutlookBarTabCtrl` объекта и использование различных методов `CMFCOutlookBarTabCtrl` класса. В примере показано включение редактирования по месту метки текст на кнопках страницу вкладки панели Outlook, включить анимацию, включите прокрутки маркеры, которые позволяют пользователю прокручивать кнопок на область панели Outlook, задать размер границы продолжение вкладку Outlook роли, а также установите выравнивание текстовые метки на панели кнопок. Этот фрагмент кода является частью [Outlook демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]  
  
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
 Указывает имя вкладки.  
  
 [in] `bDetachable`  
 Если `TRUE`, страница будет создана как отделяемой.  
  
 [in] `nImageID`  
 Индекс образа в списке внутренней изображений для изображения для отображения в новой вкладке.  
  
 [in] `dwControlBarStyle`  
 Указывает AFX_ `CBRS_`* стиль упакованного области закрепления.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для добавления элемента управления в виде новой страницы панель outlook.  
  
 Эта функция автоматически вызывает на [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).  
  
 Если задать `bDetachable` для `TRUE`, `AddControl` внутренне создает `CDockablePaneAdapter` объекта и создает оболочку для добавленного элемента управления. Класс среды выполнения окна с вкладками автоматически переключается на класс среды выполнения `CMFCOutlookBar` и класса среды выполнения с плавающей запятой кадра к `CMultiPaneFrameWnd`.  
  
### <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `AddControl` метод `CMFCOutlookBarTabCtrl` класса. Этот фрагмент кода является частью [Outlook демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 Вызывается платформой при изменении размера операции, чтобы определить, может ли отображаться Outlook панели вкладки страницы кнопки не видимы.  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если имеется несколько кнопок; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления вкладки панели Outlook динамически добавляет или удаляет вкладки из отображения в зависимости от того, сколько места доступно. Этот метод используется платформой для помощи в этом процессе.  
  
##  <a name="canshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 Вызывается платформой при изменении размера операции, чтобы определить, может ли отображаться дополнительные кнопки страницы вкладки панели Outlook не видимы.  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если имеются кнопки, которые не являются видимую в данный момент; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Элемент управления вкладки панели Outlook динамически добавляют или удаляют вкладок с экрана, в зависимости от того, сколько места доступно. Этот метод используется платформой для помощи в этом процессе.  
  
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
 Указывает исходный размер и положение, в пикселях.  
  
 [in] `pParentWnd`  
 Указатель на родительское окно. Значение не должно быть равно `NULL`.  
  
 [in] `nID`  
 Идентификатор элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент управления был создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Как правило, элементы управления вкладка панели outlook, создаваемых при [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md) элементов управления `WM_CREATE` сообщения процесса.  
  
##  <a name="enableanimation"></a>CMFCOutlookBarTabCtrl::EnableAnimation  
 Указывает, включена ли анимация, которая происходит во время переключения между активных вкладок.  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 Указывает, следует ли включить или отключить анимацию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для включения и отключения анимации. Когда пользователь открывает страницу вкладки, заголовок страницы слайды вверх или вниз, если включена анимация. При отключении анимации страницу сразу же становится активным.  
  
 Анимация включена по умолчанию.  
  
##  <a name="enableinplaceedit"></a>CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 Указывает, могут ли пользователь изменять текстовые метки на кнопках страницу вкладки панели Outlook.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Если `TRUE`, включить редактирование на месте текстовой метки. Если `FALSE`, отключите редактирования по месту.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы включить или отключить в оперативное изменение текстовых меток на кнопках страницы вкладки. По умолчанию отключен редактирования по месту.  
  
##  <a name="enablescrollbuttons"></a>CMFCOutlookBarTabCtrl::EnableScrollButtons  
 Вызывается платформой для включения дескрипторы прокрутки, позволяющие пользователю выполнять прокрутку кнопок на область панели Outlook.  
  
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
 Позволяет отображать кнопки прокрутки. Этот метод вызывается платформой при изменении активной вкладке для восстановления кнопки прокрутки.  
  
##  <a name="getbordersize"></a>CMFCOutlookBarTabCtrl::GetBorderSize  
 Возвращает размер границы элемента управления tab Outlook.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер границы в пикселях.  
  
##  <a name="getvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::GetVisiblePageButtons  

  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="isanimation"></a>CMFCOutlookBarTabCtrl::IsAnimation  
 Указывает, включена ли анимация, которая происходит во время переключения между активных вкладок.  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если анимация включена. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызовите [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) функции, чтобы включить или отключить анимации.  
  
##  <a name="ismode2003"></a>CMFCOutlookBarTabCtrl::IsMode2003  
 Определяет, является ли элемент управления вкладки панели Outlook в режиме, который эмулирует Microsoft Outlook 2003.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если в панели управления "Вкладка" Outlook находится в режиме Outlook 2003. в противном случае `FALSE`;  
  
### <a name="remarks"></a>Примечания  
 Это значение задается [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).  
  
##  <a name="onshowfewerpagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 Вызывается платформой, чтобы уменьшить число кнопок вкладки страницы, которые видны.  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод изменяет число кнопок отображения страницы при изменении размеров элемента управления.  
  
##  <a name="onshowmorepagebuttons"></a>CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 Вызывается платформой для увеличения числа кнопок вкладки страницы, которые видны.  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод задайте число кнопок вкладки страницы, которые отображаются, если размеры элемента управления.  
  
##  <a name="onshowoptions"></a>CMFCOutlookBarTabCtrl::OnShowOptions  
 Отображает **параметры области переходов** диалоговое окно.  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>Примечания  
 **Параметры области переходов** диалоговое окно позволяет пользователю укажите, какие вкладки страницы кнопки должны отображаться и порядок, в котором они отображаются.  
  
 Этот метод вызывается платформой, когда пользователь выбирает **параметры области переходов** пункта меню меню настройки элемента управления.  
  
##  <a name="setactivetab"></a>CMFCOutlookBarTabCtrl::SetActiveTab  
 Задает активной вкладки. Активной вкладки является тот, который был открыт, отображается ее содержимое.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `iTab`  
 Отсчитываемый от нуля индекс вкладки для открытия.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если указанная вкладка было установлено успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Установка активной вкладки визуальный эффект зависит от того, включена ли анимация. Дополнительные сведения см. в разделе [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).  
  
##  <a name="setbordersize"></a>CMFCOutlookBarTabCtrl::SetBorderSize  
 Задает размер границ элемента управления tab Outlook.  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `nBorderSize`  
 Указывает новый размер границы в пикселях.  
  
### <a name="remarks"></a>Примечания  
 Задает размер границ новой и повторно вычисляет макет окна outlook.  
  
##  <a name="setpagebuttontextalign"></a>CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Задает выравнивание текста меток для кнопок панели Outlook.  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiAlign`  
 Задает выравнивание текста.  
  
 [in] `bRedraw`  
 Если `TRUE`, перерисовывается окно outlook.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для изменения выравнивания текста для страницы кнопок.  
  
 `uiAlign`может принимать одно из следующих значений:  
  
|Константа|Значение|  
|--------------|-------------|  
|TA_LEFT|Выравнивание по левому краю|  
|TA_CENTER|Выравнивание по центру|  
|TA_RIGHT|Выравнивание по правому краю|  
  
 Значение по умолчанию — TA_CENTER.  
  
##  <a name="settoolbarimagelist"></a>CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Задает точечного рисунка, который содержит значки, которые отображаются в нижней части панели Outlook в режиме Outlook 2003.  
  
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
 Эта функция используется для присоединения списка изображений, изображения, которые будут отображаться на кнопки панели инструментов в режиме интеграции с Microsoft Office 2003. Индексы образа должна соответствовать страниц индексов.  
  
 Этот метод не должен вызываться не в режиме интеграции с Microsoft Office 2003. Дополнительные сведения см. в разделе [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).  
  
##  <a name="setvisiblepagebuttons"></a>CMFCOutlookBarTabCtrl::SetVisiblePageButtons  

  
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
