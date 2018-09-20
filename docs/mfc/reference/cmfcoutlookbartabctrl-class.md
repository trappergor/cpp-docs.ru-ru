---
title: Класс CMFCOutlookBarTabCtrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c4836a82c829dafee64c74237fa33c6199ace4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396913"
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl Class

Элемент управления "вкладка", который имеет внешний вид раздела **Область переходов** в Microsoft Outlook.
Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.
## <a name="syntax"></a>Синтаксис

```
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Конструктор по умолчанию.|
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Добавляет элемент управления Windows в виде новой вкладки панели Outlook.|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Вызывается платформой для определения размеров поле ввода, который отображается, когда пользователь переименовывает вкладки. (Переопределяет `CMFCBaseTabCtrl::CalcRectEdit`.)|
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Вызвано структурой во время операций по изменению размера на предмет меньшее число кнопок страниц вкладку панели Outlook могут отображаться не видимы в настоящий момент.|
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Вызвано структурой во время операций по изменению размера на предмет дополнительные кнопок страницы вкладки панели Outlook могут отображаться не видимы в настоящий момент.|
|[CMFCOutlookBarTabCtrl::Create](#create)|Создает элемент управления вкладки панели Outlook.|
|`CMFCOutlookBarTabCtrl::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Указывает, включена ли анимация, которая происходит во время переключения между вкладками active.|
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Указывает, может ли пользователь изменить текстовые метки на панели кнопок. (Переопределяет [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Вызывается платформой для включения кнопки, позволяющие пользователю выполнять прокрутку по кнопкам на область панели Outlook.|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Определяет область, которая содержит указанную точку. (Переопределяет [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Возвращает размер границы элемента управления вкладки Outlook.|
|`CMFCOutlookBarTabCtrl::GetTabArea`|Извлекает размер и положение области вкладок элемента управления вкладки. (Переопределяет [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|
|`CMFCOutlookBarTabCtrl::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Определяет, включена ли анимация, которая происходит во время переключения между вкладками active.|
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Определяет, является ли элемент управления вкладки панели Outlook в режиме, который эмулирует Microsoft Outlook 2003.|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Определяет, является ли точка внутри области вкладок. (Переопределяет [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Определяет, является ли вкладка отделяемой. (Переопределяет [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Вызывается платформой при вставке или удалить вкладку. (Переопределяет `CMFCBaseTabCtrl::OnChangeTabs`.)|
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Вызывается платформой, чтобы уменьшить число кнопок страниц, которые отображаются.|
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Вызывается платформой, чтобы увеличить число кнопок страниц, которые отображаются.|
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Отображает **параметры панели переходов** диалоговое окно.|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Повторно вычисляет внутренний макет элемента управления вкладки. (Переопределяет [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Задает активной вкладки. (Переопределяет [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Задает размер границы элемента управления вкладки Outlook.|
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Задает выравнивание текста метки на панели кнопок.|
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Задает точечного рисунка, который содержит значки, которые отображаются в нижней части панели Outlook в Outlook 2003 режиме (см. в разделе [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)).|
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||

## <a name="remarks"></a>Примечания

Чтобы создать панель Outlook с поддержкой закрепления, используйте `CMFCOutlookBar` объекта для размещения панели управления "Вкладка" Outlook. Дополнительные сведения см. в разделе [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).

## <a name="example"></a>Пример

Следующий пример демонстрирует способы инициализации `CMFCOutlookBarTabCtrl` объекта и использование различных методов `CMFCOutlookBarTabCtrl` класса. В примере показано включить редактирование на месте текстовой подписи на странице кнопок панели, включить анимацию, включите прокрутки дескрипторы, которые позволяют пользователю прокрутить кнопки на область панели Outlook, задать размер границы cont вкладку Outlook роли и набор выравнивание текстовые метки на панели кнопок. Этот фрагмент кода является частью [Outlook демонстрационного](../../visual-cpp-samples.md).

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

##  <a name="addcontrol"></a>  CMFCOutlookBarTabCtrl::AddControl

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

*pWndCtrl*<br/>
[in] Указатель на элемент управления для добавления.

*lpszName*<br/>
[in] Указывает имя вкладки.

*bDetachable*<br/>
[in] Если значение равно TRUE, страницы будут создаваться как отделяемые.

*nImageID*<br/>
[in] Индекс изображения в списке внутренних изображений для изображения для отображения в новой вкладке.

*dwControlBarStyle*<br/>
[in] Задает стиль AFX_ CBRS_ * упакованного закрепляемых панелей.

### <a name="remarks"></a>Примечания

Эта функция используется для добавления элемента управления в виде новой страницы панель outlook.

Эта функция вызывает на [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).

Если задать *bDetachable* значение true, `AddControl` внутренне создает `CDockablePaneAdapter` объекта и создает оболочку для добавляемого элемента управления. Класс среды выполнения окна с вкладками автоматически переключается на класс среды выполнения `CMFCOutlookBar` и класса среды выполнения с плавающей запятой кадра к `CMultiPaneFrameWnd`.

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `AddControl` метод в `CMFCOutlookBarTabCtrl` класса. Этот фрагмент кода является частью [Outlook демонстрационного](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

##  <a name="canshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowFewerPageButtons

Вызывается платформой при изменении размера операций, чтобы определить, может ли отображаться меньшее число кнопок страниц вкладку панели Outlook не видимы в настоящий момент.

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если имеется несколько кнопок; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Элемент управления вкладки панели Outlook динамически добавляет или удаляет вкладки из отображения в зависимости от того, сколько места. Этот метод используется платформой для помощи в этом процессе.

##  <a name="canshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowMorePageButtons

Вызывается платформой при изменении размера операций, чтобы определить, может ли отображаться дополнительные кнопок страницы вкладки панели Outlook не видимы в настоящий момент.

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если есть кнопки, которые не являются видимой в данный момент; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Элемент управления вкладки панели Outlook динамически добавляет или удаляет вкладки с экрана, в зависимости от того, сколько места. Этот метод используется платформой для помощи в этом процессе.

##  <a name="create"></a>  CMFCOutlookBarTabCtrl::Create

Создает элемент управления вкладки панели Outlook.

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*Rect*<br/>
[in] Задает первоначальный размер и положение, в пикселях.

*pParentWnd*<br/>
[in] Указатель на родительское окно. Не должен иметь значение NULL.

*nID*<br/>
[in] Идентификатор элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления был создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Как правило, элементов управления вкладки панели outlook, создаваемых при [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md) управляет сообщений WM_CREATE процесса.

##  <a name="enableanimation"></a>  CMFCOutlookBarTabCtrl::EnableAnimation

Указывает, включена ли анимация, которая происходит во время переключения между вкладками active.

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Указывает, следует ли включить или отключить анимации.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для включения и отключения анимации. Когда пользователь открывает страницу вкладки, заголовок страницы слайды вверх или вниз, если анимация включена. Если анимация отключена, страницы сразу же становится активным.

По умолчанию анимация включена.

##  <a name="enableinplaceedit"></a>  CMFCOutlookBarTabCtrl::EnableInPlaceEdit

Указывает ли пользователь может изменить текстовые метки на странице кнопок панели.

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Значение TRUE, если включите редактирование на месте текстовой метки. Если значение равно FALSE, отключите редактирование на месте.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для включения или отключения редактирование на месте меток текст на кнопках страницы вкладки. Редактирование на месте функция отключена по умолчанию.

##  <a name="enablescrollbuttons"></a>  CMFCOutlookBarTabCtrl::EnableScrollButtons

Вызывается платформой для включения прокрутки дескрипторы, позволяющие пользователю выполнять прокрутку кнопки на область панели Outlook.

```
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
[in] Определяет, отображаются ли кнопки прокрутки.

*bIsUp*<br/>
[in] Определяет, отображается ли верхний полосы прокрутки.

*bIsDown*<br/>
[in] Определяет, отображается ли полоса прокрутки вниз.

### <a name="remarks"></a>Примечания

Позволяет отображать кнопки прокрутки. Этот метод вызывается платформой при изменении активной вкладки, чтобы восстановить кнопки прокрутки.

##  <a name="getbordersize"></a>  CMFCOutlookBarTabCtrl::GetBorderSize

Возвращает размер границы элемента управления вкладки Outlook.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер границы в пикселях.

##  <a name="getvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::GetVisiblePageButtons


```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="isanimation"></a>  CMFCOutlookBarTabCtrl::IsAnimation

Указывает, включена ли анимация, которая происходит во время переключения между вкладками active.

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если анимация включена. в противном случае 0.

### <a name="remarks"></a>Примечания

Вызовите [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) функция для включения или отключения анимации.

##  <a name="ismode2003"></a>  CMFCOutlookBarTabCtrl::IsMode2003

Определяет, является ли элемент управления вкладки панели Outlook в режиме, который эмулирует Microsoft Outlook 2003.

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если в панели управления "Вкладка" Outlook находится в режиме Outlook 2003; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Это значение задается [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).

##  <a name="onshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowFewerPageButtons

Вызывается платформой, чтобы уменьшить число кнопок страниц, которые отображаются.

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>Примечания

Этот метод изменяет количество кнопок вкладки отображения страницы, при изменении размера элемента управления.

##  <a name="onshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowMorePageButtons

Вызывается платформой, чтобы увеличить число кнопок страниц, которые отображаются.

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>Примечания

Этот метод регулировать число кнопок страниц, которые отображаются при изменении размера элемента управления.

##  <a name="onshowoptions"></a>  CMFCOutlookBarTabCtrl::OnShowOptions

Отображает **параметры панели переходов** диалоговое окно.

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>Примечания

**Параметры панели переходов** диалоговое окно позволяет пользователю select, являющиеся кнопок вкладки страницы для отображения и порядок, в котором они отображаются.

Этот метод вызывается платформой, когда пользователь выбирает **параметры панели переходов** пункт меню меню настройки элемента управления.

##  <a name="setactivetab"></a>  CMFCOutlookBarTabCtrl::SetActiveTab

Задает активной вкладки. Активной вкладкой является тот, который был открыт, его видимым содержимым.

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>Параметры

*iTab*<br/>
[in] Отсчитываемый от нуля индекс вкладки, должны быть открыты.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если указанная вкладка было установлено успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Визуальный эффект настройки активной вкладкой зависит от того, включена ли анимация. Дополнительные сведения см. в разделе [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).

##  <a name="setbordersize"></a>  CMFCOutlookBarTabCtrl::SetBorderSize

Задает размер границы элемента управления вкладки Outlook.

```
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>Параметры

*nBorderSize*<br/>
[in] Указывает новый размер границы в пикселях.

### <a name="remarks"></a>Примечания

Задает новый размер границы и повторно вычисляет макет окна outlook.

##  <a name="setpagebuttontextalign"></a>  CMFCOutlookBarTabCtrl::SetPageButtonTextAlign

Задает выравнивание текста метки на панели кнопок.

```
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*uiAlign*<br/>
[in] Задает выравнивание текста.

*bRedraw*<br/>
[in] Если значение равно TRUE, в окне outlook перерисовку.

### <a name="remarks"></a>Примечания

Эту функцию можно используйте для изменения выравнивания текста для кнопки страницы.

*uiAlign* может принимать одно из следующих значений:

|Константа|Значение|
|--------------|-------------|
|TA_LEFT|Выравнивание по левому краю|
|TA_CENTER|Выравнивание по центру|
|TA_RIGHT|Выравнивание по правому краю|

Значение по умолчанию — TA_CENTER.

##  <a name="settoolbarimagelist"></a>  CMFCOutlookBarTabCtrl::SetToolbarImageList

Задает точечного рисунка, который содержит значки, которые отображаются в нижней части панели Outlook в Outlook 2003 режиме.

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
[in] Указывает идентификатор ресурса изображения для загрузки.

*CX*<br/>
[in] Задает ширину изображения в списке изображений в пикселях.

*clrTransp*<br/>
[in] Значение RGB, указывающий прозрачный цвет.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если выполнение прошло успешно; в противном случае возвращает значение FALSE.

### <a name="remarks"></a>Примечания

Эта функция используется для присоединения к списку изображений, изображений которых будут отображаться на кнопки панели инструментов в режиме Microsoft Office 2003. Индексы образа должна соответствовать страницы индексов.

Этот метод не должен вызываться не в Microsoft Office 2003 режиме. Дополнительные сведения см. в разделе [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).

##  <a name="setvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::SetVisiblePageButtons


```
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>Параметры

[in] *nVisiblePageButtons*

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[Класс CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)
