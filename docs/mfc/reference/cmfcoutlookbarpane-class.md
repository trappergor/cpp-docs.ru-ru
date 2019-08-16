---
title: Класс CMFCOutlookBarPane
ms.date: 11/04/2016
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
ms.openlocfilehash: 9ef6a06a4889119e39e72a9e495e5d4f9e17cf56
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505151"
---
# <a name="cmfcoutlookbarpane-class"></a>Класс CMFCOutlookBarPane

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

Элемент управления, производный от [класса CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) , который можно вставить в панель Outlook ( [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)). Область панели Outlook содержит столбец больших кнопок. Пользователь может прокрутить список с кнопками вверх и вниз, если он больше области, в которой отображается. Когда пользователь окончательно удаляет область панели Outlook из панели Outlook, она может стать плавающей или прикрепиться к окну основного фрейма.

## <a name="syntax"></a>Синтаксис

```
class CMFCOutlookBarPane : public CMFCToolBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Конструктор по умолчанию.|
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCOutlookBarPane:: AddButton](#addbutton)|Добавляет кнопку в панель Outlook.|
|[CMFCOutlookBarPane:: Канбеаттачед](#canbeattached)|Определяет, можно ли закрепить панель в другой области или окне фрейма. (Переопределяет [CBasePane:: канбеаттачед](../../mfc/reference/cbasepane-class.md#canbeattached).)|
|`CMFCOutlookBarPane::CanBeRestored`|Определяет, может ли система восстановить исходное состояние панели инструментов после настройки. (Переопределяет [CMFCToolBar:: канбересторед](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCOutlookBarPane:: ClearAll](#clearall)|Освобождает ресурсы, используемые образами на панели Outlook.|
|[CMFCOutlookBarPane:: Create](#create)|Создает панель Outlook.|
|`CMFCOutlookBarPane::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCOutlookBarPane::Dock`|Вызывается платформой для закрепления панели панели Outlook. (Переопределяет `CPane::Dock`.)|
|[CMFCOutlookBarPane:: Енаблепажескроллмоде](#enablepagescrollmode)|Указывает, прокручивается ли стрелки прокрутки в области панели Outlook к списку кнопок по страницам или по кнопке.|
|[CMFCOutlookBarPane:: Жетрегуларколор](#getregularcolor)|Возвращает обычный (не выбранный) цвет текста панели Outlook.|
|`CMFCOutlookBarPane::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[CMFCOutlookBarPane:: Исбаккграундтекстуре](#isbackgroundtexture)|Определяет, загружено ли фоновое изображение для панели Outlook.|
|`CMFCOutlookBarPane::IsChangeState`|Определяет, может ли быть закреплена Плавающая панель. (Переопределяет `CPane::IsChangeState`.)|
|[CMFCOutlookBarPane:: Исдравшадедхигхлигхт](#isdrawshadedhighlight)|Определяет, затенена ли граница кнопки при выделении кнопки и отображении фонового изображения.|
|`CMFCOutlookBarPane::OnBeforeFloat`|Вызывается структурой, когда область перемещается в float. (Переопределяет [CPane:: онбефорефлоат](../../mfc/reference/cpane-class.md#onbeforefloat).)|
|[CMFCOutlookBarPane:: Ремовебуттон](#removebutton)|Удаляет кнопку с указанным ИДЕНТИФИКАТОРом команды.|
|`CMFCOutlookBarPane::RestoreOriginalstate`|Восстанавливает первоначальное состояние панели инструментов. (Переопределяет [CMFCToolBar:: рестореоригиналстате](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|
|[CMFCOutlookBarPane:: Сетбаккколор](#setbackcolor)|Задает цвет фона.|
|[CMFCOutlookBarPane:: Сетбаккимаже](#setbackimage)|Задает фоновое изображение.|
|[CMFCOutlookBarPane:: Сетдефаултстате](#setdefaultstate)|Сбрасывает панель Outlook к исходному набору кнопок.|
|[CMFCOutlookBarPane:: Сетекстраспаце](#setextraspace)|Задает число пикселей заполнения, используемое вокруг кнопок в области панели Outlook.|
|[CMFCOutlookBarPane:: Сеттекстколор](#settextcolor)|Задает цвета обычного и выделенного текста в области панели Outlook.|
|[CMFCOutlookBarPane:: Сеттранспарентколор](#settransparentcolor)|Задает прозрачный цвет для панели Outlook.|
|`CMFCOutlookBarPane::SmartUpdate`|Используется для внутренних целей для обновления панели Outlook. (Переопределяет `CMFCToolBar::SmartUpdate`.)|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CMFCOutlookBarPane:: Енаблеконтекстменуитемс](#enablecontextmenuitems)|Указывает, какие пункты контекстного меню отображаются в режиме настройки.|
|[CMFCOutlookBarPane:: Ремовеаллбуттонс](#removeallbuttons)|Удаляет все кнопки с панели Outlook. (Переопределяет [CMFCToolBar:: ремовеаллбуттонс](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|

## <a name="remarks"></a>Примечания

Сведения о том, как реализовать панель Outlook, см. в разделе [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).

Пример панели Outlook см. в примере проекта Аутлукдемо.

## <a name="example"></a>Пример

В следующем примере показано, как использовать различные методы `CMFCOutlookBarPane` класса. В этом примере показано, как создать панель Outlook, включить режим прокрутки страницы, включить закрепление и задать цвет фона для панели Outlook. Этот фрагмент кода является частью примера " [множественные представления Outlook](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[кмфкбасетулбар](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афксаутлукбарпане. h

##  <a name="addbutton"></a>CMFCOutlookBarPane:: AddButton

Добавляет кнопку в панель Outlook.

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

*уиимаже*<br/>
окне Указывает идентификатор ресурса точечного рисунка.

*лпсзлабел*<br/>
окне Задает текст кнопки.

*иидкомманд*<br/>
окне Задает идентификатор элемента управления "Кнопка".

*иинсертат*<br/>
окне Указывает отсчитываемый от нуля индекс на странице панели Outlook, с которой нужно вставить кнопку.

*уилабел*<br/>
окне Идентификатор строкового ресурса.

*сзбмпфиленаме*<br/>
окне Указывает имя загружаемого файла образа диска.

*сзлабел*<br/>
окне Задает текст кнопки.

*хбмп*<br/>
окне Маркер для точечного рисунка кнопки.

*hIcon*<br/>
окне Маркер значка кнопок.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка была успешно добавлена; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Этот метод используется для вставки новой кнопки в страницу панели Outlook. Изображение этой кнопки можно загрузить либо из ресурсов приложения, либо из файла на диске.

Если идентификатор страницы, указанный параметром *уипажеид* , равен-1, кнопка вставляется в первую страницу.

Если индекс, указанный параметром *иинсертат* , равен-1, то кнопка добавляется в конец страницы.

##  <a name="canbeattached"></a>CMFCOutlookBarPane:: Канбеаттачед

Дополнительные сведения см. в исходном коде, расположенном в папке **VC\\atlmfc\\src\\mfc** каталога установки Visual Studio.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

##  <a name="clearall"></a>CMFCOutlookBarPane:: ClearAll

Освобождает ресурсы, используемые образами на панели Outlook.

```
void ClearAll();
```

### <a name="remarks"></a>Примечания

Этот метод напрямую вызывает [кмфктулбаримажес:: Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear), который вызывается для изображений, используемых в области панели Outlook.

##  <a name="create"></a>CMFCOutlookBarPane:: Create

Создает панель Outlook.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,
    UINT uiID=(UINT)-1,
    DWORD dwControlBarStyle=0);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
окне Задает родительское окно элемента управления панели Outlook. Не может иметь значение NULL.

*двстиле*<br/>
окне Стиль окна.  Список стилей окна см. в разделе [стили окон](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*uiID*<br/>
окне Идентификатор элемента управления. Должен быть уникальным, чтобы обеспечить сохранение состояния элемента управления.

*двконтролбарстиле*<br/>
окне Задает специальные стили, определяющие поведение элемента управления панели Outlook при его отсоединении от панели Outlook.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Для создания `CMFCOutlookBarPane` объекта сначала необходимо вызвать конструктор, а затем вызвать метод `Create`, который создает элемент управления панели Outlook и `CMFCOutlookBarPane` присоединяет его к объекту.

Дополнительные сведения о `dwControlBarStyle` см. в разделе [CBasePane:: креатикс](../../mfc/reference/cbasepane-class.md#createex).

##  <a name="enablecontextmenuitems"></a>CMFCOutlookBarPane:: Енаблеконтекстменуитемс

Указывает, какие пункты контекстного меню отображаются в режиме настройки.

```
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,
    CMenu* pPopup);
```

### <a name="parameters"></a>Параметры

*пбуттон*<br/>
окне Указатель на кнопку на панели инструментов, которую щелкнул пользователь.

*ппопуп*<br/>
окне Указатель на контекстное меню.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если контекстное меню должно отображаться; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Переопределите этот метод, чтобы изменить стандартное контекстное меню платформы, которое платформа отображает в режиме настройки.

Реализация по умолчанию проверяет режим настройки ( [CMFCToolBar:: искустомиземоде](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)) и, если он имеет значение true, отключает все пункты контекстного меню, кроме **Delete**. Затем он просто передает входные параметры в `CMFCToolBar::EnableContextMenuItems`.

> [!NOTE]
> *Контекстное меню* является синонимом контекстного меню.

##  <a name="enablepagescrollmode"></a>CMFCOutlookBarPane:: Енаблепажескроллмоде

Указывает, прокручивается ли стрелки прокрутки в области панели Outlook к списку кнопок на странице или по кнопке.

```
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```

### <a name="parameters"></a>Параметры

*бпажескролл*<br/>
окне Если значение — TRUE, включите режим прокрутки страницы. Если значение равно FALSE, отключите режим прокрутки страницы.

##  <a name="getregularcolor"></a>CMFCOutlookBarPane:: Жетрегуларколор

Возвращает обычный (невыбранный) цвет текста панели Outlook.

```
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий цвет текста в виде значения цвета RGB.

### <a name="remarks"></a>Примечания

Используйте [CMFCOutlookBarPane:: сеттекстколор](#settextcolor) , чтобы установить текущий (обычный и выбранный) цвет текста панели Outlook. Цвет текста по умолчанию можно получить, вызвав функцию [жетсисколор](/windows/win32/api/winuser/nf-winuser-getsyscolor) с индексом COLOR_WINDOW.

##  <a name="isbackgroundtexture"></a>CMFCOutlookBarPane:: Исбаккграундтекстуре

Определяет, загружено ли фоновое изображение для панели Outlook.

```
BOOL IsBackgroundTexture() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если имеется фоновое изображение для показа; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Фоновое изображение можно добавить, вызвав функцию [CMFCOutlookBarPane:: сетбаккимаже](#setbackimage) .

Если фоновое изображение отсутствует, фон закрашивается цветом, заданным с помощью [CMFCOutlookBarPane:: сетбаккколор](#setbackcolor).

##  <a name="isdrawshadedhighlight"></a>CMFCOutlookBarPane:: Исдравшадедхигхлигхт

Определяет, затенена ли граница кнопки при выделении кнопки и отображении фонового изображения.

```
BOOL IsDrawShadedHighlight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если границы кнопки затенены; в противном случае — FALSE.

##  <a name="removeallbuttons"></a>CMFCOutlookBarPane:: Ремовеаллбуттонс

Удаляет все кнопки с панели Outlook.

```
virtual void RemoveAllButtons();
```

##  <a name="removebutton"></a>CMFCOutlookBarPane:: Ремовебуттон

Удаляет кнопку с указанным ИДЕНТИФИКАТОРом команды.

```
BOOL RemoveButton(UINT iIdCommand);
```

### <a name="parameters"></a>Параметры

*иидкомманд*<br/>
окне Указывает идентификатор команды удаляемой кнопки.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кнопка была успешно удалена; Значение FALSE, если указан недопустимый идентификатор команды.

##  <a name="setbackcolor"></a>CMFCOutlookBarPane:: Сетбаккколор

Задает цвет фона панели Outlook.

```
void SetBackColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
[in] Задает новый цвет фона.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы задать текущий цвет фона для панели Outlook. Цвет фона используется только при отсутствии фонового изображения.

##  <a name="setbackimage"></a>CMFCOutlookBarPane:: Сетбаккимаже

Задает фоновое изображение.

```
void SetBackImage(UINT uiImageID);
```

### <a name="parameters"></a>Параметры

*уиимажеид*<br/>
окне Указывает идентификатор ресурса изображения.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы задать фоновое изображение в панели Outlook. Список фоновых изображений управляется внедренным объектом [класса кмфктулбаримажес](../../mfc/reference/cmfctoolbarimages-class.md) .

##  <a name="setdefaultstate"></a>CMFCOutlookBarPane:: Сетдефаултстате

Сбрасывает панель Outlook к исходному набору кнопок.

```
void SetDefaultState();
```

### <a name="remarks"></a>Примечания

Этот метод восстанавливает исходный набор кнопок панели Outlook. Этот метод подобен `CMFCOutlookBarPane::RestoreOriginalstate`, за исключением того, что он не запускает перерисовку панели Outlook.

##  <a name="setextraspace"></a>CMFCOutlookBarPane:: Сетекстраспаце

Задает число пикселей заполнения, используемое вокруг кнопок в области панели Outlook.

```
void SetExtraSpace()
```

##  <a name="settextcolor"></a>CMFCOutlookBarPane:: Сеттекстколор

Задает цвета обычного и выделенного текста в области панели Outlook.

```
void SetTextColor(
    COLORREF clrRegText,
    COLORREF clrSelText=0);
```

### <a name="parameters"></a>Параметры

*клррегтекст*<br/>
окне Задает новый цвет для невыделенного текста.

*клрселтекст*<br/>
окне Задает новый цвет для выделенного текста.

##  <a name="settransparentcolor"></a>CMFCOutlookBarPane:: Сеттранспарентколор

Задает прозрачный цвет для панели Outlook.

```
void SetTransparentColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*color*<br/>
Задает новый прозрачный цвет.

### <a name="remarks"></a>Примечания

Прозрачный цвет необходим для вывода прозрачных изображений. Любое вхождение этого цвета в изображении закрашивается цветом фона.  Не существует смешивания фоновых и передних изображений.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[Класс CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
