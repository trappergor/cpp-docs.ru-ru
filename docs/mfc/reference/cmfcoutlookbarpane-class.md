---
title: Класс CMFCOutlookBarPane | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2d468ded9db1d21fd19bc553ed2a0c3227725a0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075558"
---
# <a name="cmfcoutlookbarpane-class"></a>Класс CMFCOutlookBarPane

Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.

Элемент управления, производный от [класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) , может быть вставлен на панель Outlook ( [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)). Область панели Outlook содержит столбец больших кнопок. Пользователь может прокрутить список с кнопками вверх и вниз, если он больше области, в которой отображается. Когда пользователь окончательно удаляет область панели Outlook из панели Outlook, она может стать плавающей или прикрепиться к окну основного фрейма.

## <a name="syntax"></a>Синтаксис

```
class CMFCOutlookBarPane : public CMFCToolBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Конструктор по умолчанию.|
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCOutlookBarPane::AddButton](#addbutton)|Добавляет кнопку область панели Outlook.|
|[CMFCOutlookBarPane::CanBeAttached](#canbeattached)|Определяет, закреплением области к другой панели или окне фрейма. (Переопределяет [CBasePane::CanBeAttached](../../mfc/reference/cbasepane-class.md#canbeattached).)|
|`CMFCOutlookBarPane::CanBeRestored`|Определяет, будет ли система может восстановиться панель инструментов в исходное состояние после настройки. (Переопределяет [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCOutlookBarPane::ClearAll](#clearall)|Освобождает ресурсы, используемые изображения в область панели Outlook.|
|[CMFCOutlookBarPane::Create](#create)|Создает область панели Outlook.|
|`CMFCOutlookBarPane::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCOutlookBarPane::Dock`|Вызывается платформой, чтобы закрепить область панели Outlook. (Переопределяет `CPane::Dock`.)|
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|Указывает ли стрелки прокрутки на область панели Outlook переместить список кнопок, страницы или кнопки.|
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Возвращает цвет обычного текста (не выбрано) область панели Outlook.|
|`CMFCOutlookBarPane::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Определяет, существует ли фоновое изображение загружается для область панели Outlook.|
|`CMFCOutlookBarPane::IsChangeState`|Определяет, может быть закреплено плавающую панель. (Переопределяет `CPane::IsChangeState`.)|
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Определяет, является ли граница кнопки затененную при кнопки выделяется и отображается фонового изображения.|
|`CMFCOutlookBarPane::OnBeforeFloat`|Вызывается платформой, когда область будет о число с плавающей запятой. (Переопределяет [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|Удаляет кнопка с указанным идентификатором команды.|
|`CMFCOutlookBarPane::RestoreOriginalstate`|Восстанавливает первоначальное состояние панели инструментов. (Переопределяет [CMFCToolBar::RestoreOriginalState](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Задает цвет фона.|
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Задает фоновое изображение.|
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Сбрасывает область панели Outlook на исходный набор кнопок.|
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Задает количество пикселей, заполнения, используемого вокруг кнопки в область панели Outlook.|
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Задает цвета обычных и выделенный текст в область панели Outlook.|
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Задает прозрачный цвет для область панели Outlook.|
|`CMFCOutlookBarPane::SmartUpdate`|Используется внутренним образом для обновления панели Outlook. (Переопределяет `CMFCToolBar::SmartUpdate`.)|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|Указывает, какие пункты контекстного меню отображаются в режим настройки.|
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Удаляет все кнопки из область панели Outlook. (Переопределяет [CMFCToolBar::RemoveAllButtons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|

## <a name="remarks"></a>Примечания

Сведения о том, как реализовать панель Outlook, см. в разделе [класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).

Например, панель Outlook см. в разделе OutlookDemo примера проекта.

## <a name="example"></a>Пример

В следующем примере показано, как использовать различные методы `CMFCOutlookBarPane` класса. В примере показано создание область панели Outlook, включить режим прокрутки страниц, Включение закрепления и задать цвет фона панели. Этот фрагмент кода является частью [пример Outlook с несколькими представлениями](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxoutlookbarpane.h

##  <a name="addbutton"></a>  CMFCOutlookBarPane::AddButton

Добавляет кнопку область панели Outlook.

```
BOOL AddButton(
    UINT uiImage,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    UINT uiImage,
    UINT uiLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    LPCTSTR szBmpFileName,
    LPCTSTR szLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HBITMAP hBmp,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HICON hIcon,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1,
    BOOL bAlphaBlend=FALSE);
```

### <a name="parameters"></a>Параметры

*uiImage*<br/>
[in] Указывает идентификатор ресурса растрового изображения.

*lpszLabel*<br/>
[in] Задает текст кнопки.

*iIdCommand*<br/>
[in] Указывает идентификатор элемента управления button.

*iInsertAt*<br/>
[in] Отсчитываемый от нуля индекс указывает на странице панели outlook, по которому следует вставить кнопку.

*uiLabel*<br/>
[in] Идентификатор ресурса строки.

*szBmpFileName*<br/>
[in] Задает имя файла образа диска для загрузки.

*szLabel*<br/>
[in] Задает текст кнопки.

*hBmp*<br/>
[in] Дескриптор точечного рисунка для кнопки.

*hIcon*<br/>
[in] Дескриптор значка для кнопки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка был успешно добавлен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод позволяет вставить новую кнопку на страницу панели Outlook. Изображение кнопки можно загрузить из ресурсов приложения или из файла на диске.

Если идентификатор страницы, указанный параметром *uiPageID* равно -1, кнопка будет вставлена в первой страницы.

Если указанный индекс *iInsertAt* равно -1, будет добавлена кнопка, в конце страницы.

##  <a name="canbeattached"></a>  CMFCOutlookBarPane::CanBeAttached

Для получения дополнительных сведений см. в разделе исходном коде, расположенном в **VC\\atlmfc\\src\\mfc** папке установки Visual Studio.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="clearall"></a>  CMFCOutlookBarPane::ClearAll

Освобождает ресурсы, используемые образы в область панели Outlook.

```
void ClearAll();
```

### <a name="remarks"></a>Примечания

Этот метод напрямую вызывает [CMFCToolBarImages::Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), который вызывается в образах, используемых область панели Outlook.

##  <a name="create"></a>  CMFCOutlookBarPane::Create

Создает область панели Outlook.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,
    UINT uiID=(UINT)-1,
    DWORD dwControlBarStyle=0);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
[in] Указывает родительского окна элемента управления панели панель Outlook. Не должен иметь значение NULL.

*dwStyle*<br/>
[in] Стиль окна.  Список стилей окна, см. в разделе [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*uiID*<br/>
[in] Идентификатор элемента управления. Должно быть уникальным, чтобы включить сохранение состояния элемента управления.

*dwControlBarStyle*<br/>
[in] Указывает специальные стили, которые определяют поведение элемента управления область панели Outlook при отсоединении их от панели Outlook.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Для создания `CMFCOutlookBarPane` объект, сначала вызовите конструктор, а затем вызовите `Create`, который создает панели элемента управления панели Outlook и присоединяет его к `CMFCOutlookBarPane` объекта.

Дополнительные сведения о `dwControlBarStyle` см. в разделе [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

##  <a name="enablecontextmenuitems"></a>  CMFCOutlookBarPane::EnableContextMenuItems

Указывает, какие пункты контекстного меню отображаются в режим настройки.

```
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,
    CMenu* pPopup);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
[in] Указатель на кнопку панели инструментов, нажимает пользователь.

*pPopup*<br/>
[in] Указатель в контекстном меню.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если должны отображаться в контекстном меню; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы изменить стандартный контекстное меню framework, платформа отображает в режим настройки.

Реализация по умолчанию проверяет режим настройки ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) и если он устанавливается в значение TRUE отключает все сочетания элементов меню, за исключением **удалить**. После этого он просто передает входные параметры `CMFCToolBar::EnableContextMenuItems`.

> [!NOTE]
> *Контекстное меню* является синонимом для контекстного меню.

##  <a name="enablepagescrollmode"></a>  CMFCOutlookBarPane::EnablePageScrollMode

Указывает ли стрелки прокрутки на область панели Outlook переместить список кнопок страницу за страницей, или кнопку, кнопку.

```
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```

### <a name="parameters"></a>Параметры

*bPageScroll*<br/>
[in] Значение TRUE, если включите режим прокрутки страницы. Если значение равно FALSE, отключите режим прокрутки страниц.

##  <a name="getregularcolor"></a>  CMFCOutlookBarPane::GetRegularColor

Возвращает обычному (то есть невыделенные) цвет текста область панели Outlook.

```
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий цвет текста как значение RGB.

### <a name="remarks"></a>Примечания

Используйте [CMFCOutlookBarPane::SetTextColor](#settextcolor) задать текущий цвет текста (обычные и выбранного) панели Outlook. Цвет текста по умолчанию можно получить, вызвав [GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor) функции с индексом COLOR_WINDOW.

##  <a name="isbackgroundtexture"></a>  CMFCOutlookBarPane::IsBackgroundTexture

Определяет, существует ли фоновое изображение загружается для область панели Outlook.

```
BOOL IsBackgroundTexture() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если фоновое изображение для отображения; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Фоновое изображение можно добавить, вызвав [CMFCOutlookBarPane::SetBackImage](#setbackimage) функции.

Если фоновое изображение отсутствует, фон закрашивается с цвет, указанный с помощью [CMFCOutlookBarPane::SetBackColor](#setbackcolor).

##  <a name="isdrawshadedhighlight"></a>  CMFCOutlookBarPane::IsDrawShadedHighlight

Определяет, является ли граница кнопки затененную при кнопки выделяется и отображается фонового изображения.

```
BOOL IsDrawShadedHighlight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если границы кнопки затенены; в противном случае — значение FALSE.

##  <a name="removeallbuttons"></a>  CMFCOutlookBarPane::RemoveAllButtons

Удаляет все кнопки из область панели Outlook.

```
virtual void RemoveAllButtons();
```

##  <a name="removebutton"></a>  CMFCOutlookBarPane::RemoveButton

Удаляет кнопка с указанным идентификатором команды.

```
BOOL RemoveButton(UINT iIdCommand);
```

### <a name="parameters"></a>Параметры

*iIdCommand*<br/>
[in] Указывает идентификатор команды кнопки для удаления.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопки был успешно удален; Значение FALSE, если заданный идентификатор команды не является допустимым.

##  <a name="setbackcolor"></a>  CMFCOutlookBarPane::SetBackColor

Задает цвет фона панели Outlook.

```
void SetBackColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
[in] Указывает новый цвет фона.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы задать текущий цвет фона панели Outlook. Цвет фона используется только в том случае, если имеется фоновое изображение отсутствует.

##  <a name="setbackimage"></a>  CMFCOutlookBarPane::SetBackImage

Задает фоновое изображение.

```
void SetBackImage(UINT uiImageID);
```

### <a name="parameters"></a>Параметры

*uiImageID*<br/>
[in] Указывает идентификатор ресурса изображения.

### <a name="remarks"></a>Примечания

Вызовите этот метод для установки Outlook линейки фонового изображения. Осуществляется список фоновых изображений, внедренных [класс CMFCToolBarImages](../../mfc/reference/cmfctoolbarimages-class.md) объекта.

##  <a name="setdefaultstate"></a>  CMFCOutlookBarPane::SetDefaultState

Сбрасывает область панели Outlook на исходный набор кнопок.

```
void SetDefaultState();
```

### <a name="remarks"></a>Примечания

Этот метод восстанавливает исходный набор кнопок панели Outlook. Этот метод аналогичен `CMFCOutlookBarPane::RestoreOriginalstate`, за исключением того, что это не вызывает перерисовывает область панели Outlook.

##  <a name="setextraspace"></a>  CMFCOutlookBarPane::SetExtraSpace

Задает количество пикселей, заполнения, используемого вокруг кнопки в область панели Outlook.

```
void SetExtraSpace()
```

##  <a name="settextcolor"></a>  CMFCOutlookBarPane::SetTextColor

Задает цвета обычных и выделенный текст в область панели Outlook.

```
void SetTextColor(
    COLORREF clrRegText,
    COLORREF clrSelText=0);
```

### <a name="parameters"></a>Параметры

*clrRegText*<br/>
[in] Указывает новый цвет для невыбранных текста.

*clrSelText*<br/>
[in] Указывает новый цвет выделенного текста.

##  <a name="settransparentcolor"></a>  CMFCOutlookBarPane::SetTransparentColor

Задает прозрачный цвет для область панели Outlook.

```
void SetTransparentColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Указывает новый прозрачный цвет.

### <a name="remarks"></a>Примечания

Прозрачный цвет необходим для отображения прозрачные изображения. Все вхождения этот цвет в изображения закрашивается вместо цветом фона.  Нет, не наложения изображений фона и переднего плана.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[Класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
