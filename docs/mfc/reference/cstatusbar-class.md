---
title: Класс CStatusBar
ms.date: 11/04/2016
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
ms.openlocfilehash: 48de31d95814ce5fc1fb015e69cf38d73337cb79
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502337"
---
# <a name="cstatusbar-class"></a>Класс CStatusBar

Панель элементов управления со строкой областей текстового вывода или "индикаторов".

## <a name="syntax"></a>Синтаксис

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CStatusBar:: CStatusBar](#cstatusbar)|Создает объект `CStatusBar`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CStatusBar:: Коммандтоиндекс](#commandtoindex)|Возвращает индекс для заданного идентификатора индикатора.|
|[CStatusBar:: Create](#create)|Создает строку состояния, прикрепляет ее к `CStatusBar` объекту и задает исходный шрифт и высоту строки.|
|[CStatusBar:: Креатикс](#createex)|Создает объект с дополнительными стилями для внедренного `CStatusBarCtrl` объекта. `CStatusBar`|
|[CStatusBar::D Равитем](#drawitem)|Вызывается при изменении визуального аспекта элемента управления строки состояния, рисуемого владельцем.|
|[CStatusBar:: Жетитемид](#getitemid)|Возвращает идентификатор индикатора для заданного индекса.|
|[CStatusBar:: Жетитемрект](#getitemrect)|Возвращает отображаемый прямоугольник для заданного индекса.|
|[CStatusBar:: Жетпанеинфо](#getpaneinfo)|Возвращает идентификатор индикатора, стиль и ширину для заданного индекса.|
|[CStatusBar:: Жетпанестиле](#getpanestyle)|Возвращает стиль индикатора для заданного индекса.|
|[CStatusBar:: Жетпанетекст](#getpanetext)|Возвращает текст индикатора для заданного индекса.|
|[CStatusBar:: Жетстатусбарктрл](#getstatusbarctrl)|Разрешает прямой доступ к базовому общему элементу управления.|
|[CStatusBar:: Сетиндикаторс](#setindicators)|Задает идентификаторы индикаторов.|
|[CStatusBar:: Сетпанеинфо](#setpaneinfo)|Задает идентификатор индикатора, стиль и ширину для заданного индекса.|
|[CStatusBar:: Сетпанестиле](#setpanestyle)|Задает стиль индикатора для заданного индекса.|
|[CStatusBar:: Сетпанетекст](#setpanetext)|Задает текст индикатора для заданного индекса.|

## <a name="remarks"></a>Примечания

Области вывода обычно используются в качестве линий сообщений и в качестве индикаторов состояния. Примеры включают в себя строки справки меню, поясняющие выбранную команду меню, и индикаторы, отображающие состояние блокировки прокрутки, NUM LOCK и других клавиш.

[CStatusBar:: жетстатусбарктрл](#getstatusbarctrl), функция-член, новая для MFC 4,0, позволяет воспользоваться преимуществами поддержки общего элемента управления Windows для настройки строки состояния и дополнительных функций. `CStatusBar`функции элементов предоставляют большую часть функциональных возможностей стандартных элементов управления Windows. Однако при вызове `GetStatusBarCtrl`вы можете присвоить строкам состояния еще больше характеристик строки состояния Windows 95/98. При вызове `GetStatusBarCtrl`будет возвращена ссылка `CStatusBarCtrl` на объект. Дополнительные сведения о проектировании панелей инструментов с помощью стандартных элементов управления Windows см. в разделе [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) . Дополнительные общие сведения об общих элементах управления см. в разделе [Общие элементы управления](/windows/win32/Controls/common-controls-intro) в Windows SDK.

Платформа хранит сведения о индикаторе в массиве с крайним левым индикатором в позиции 0. При создании строки состояния используется массив идентификаторов строк, которые платформа связывает с соответствующими индикаторами. Затем можно использовать строковый идентификатор или индекс для доступа к индикатору.

По умолчанию первым индикатором является "эластичность": он занимает длину строки состояния, не используемой другими панелями индикаторов, чтобы другие панели были выровняться по правому краю.

Чтобы создать строку состояния, выполните следующие действия.

1. `CStatusBar` Создайте объект.

1. Вызовите функцию [CREATE](#create) (или [креатикс](#createex)), чтобы создать окно строки состояния и присоединить `CStatusBar` его к объекту.

1. Вызовите [сетиндикаторс](#setindicators) , чтобы связать идентификатор строки с каждым индикатором.

Существует три способа обновления текста в области строки состояния.

1. Вызовите [CWnd:: SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) , чтобы обновить текст только в области 0.

1. Вызовите [Поддержка CCmdUI:: SetText](../../mfc/reference/ccmdui-class.md#settext) в ОБРАБОТЧИКе ON_UPDATE_COMMAND_UI в строке состояния.

1. Вызовите [сетпанетекст](#setpanetext) , чтобы обновить текст для любой панели.

Вызовите [сетпанестиле](#setpanestyle) , чтобы обновить стиль области строки состояния.

Дополнительные сведения об использовании `CStatusBar`см. в статье [Реализация строки состояния в MFC и](../../mfc/status-bar-implementation-in-mfc.md) [в техническом примечании 31. Панели](../../mfc/tn031-control-bars.md)элементов управления.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>Требования

**Заголовок:** афксекст. h

##  <a name="commandtoindex"></a>CStatusBar:: Коммандтоиндекс

Возвращает индекс индикатора для заданного идентификатора.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Параметры

*нидфинд*<br/>
Идентификатор строки индикатора, индекс которого необходимо получить.

### <a name="return-value"></a>Возвращаемое значение

Индекс индикатора, если он успешно выполнен; -1, если это не удалось.

### <a name="remarks"></a>Примечания

Индекс первого индикатора равен 0.

##  <a name="create"></a>CStatusBar:: Create

Создает строку состояния (дочернее окно) и связывает ее с `CStatusBar` объектом.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , окно окна которого является родительским по отношению к строке состояния.

*двстиле*<br/>
Стиль строки состояния. В дополнение к стандартным [стилям](../../mfc/reference/styles-used-by-mfc.md#window-styles)Windows эти стили поддерживаются.

- Панель управления CBRS_TOP находится в верхней части окна фрейма.

- Панель элементов управления CBRS_BOTTOM находится в нижней части окна фрейма.

- CBRS_NOALIGN панель управления не перемещается при изменении размера родительского элемента.

*nID*<br/>
Идентификатор дочернего окна панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Также задает исходный шрифт и задает для высоты строки состояния значение по умолчанию.

##  <a name="createex"></a>CStatusBar:: Креатикс

Вызовите эту функцию, чтобы создать строку состояния (дочернее окно) и связать ее `CStatusBar` с объектом.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , окно окна которого является родительским по отношению к строке состояния.

*двктрлстиле*<br/>
Дополнительные стили для создания внедренного объекта [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) . Значение по умолчанию указывает строку состояния без поддержки захвата изменения размера или подсказок. Поддерживаются следующие стили строки состояния:

- SBARS_SIZEGRIP. элемент управления "строка состояния" включает захват изменения размера в правом конце строки состояния. Захват изменения размера аналогичен границе изменения размера; это прямоугольная область, которую пользователь может щелкнуть и перетащить, чтобы изменить размер родительского окна.

- SBT_TOOLTIPS. строка состояния поддерживает подсказки.

Дополнительные сведения об этих стилях см. [в разделе Параметры для CStatusBarCtrl](../../mfc/settings-for-the-cstatusbarctrl.md).

*двстиле*<br/>
Стиль строки состояния. Значение по умолчанию указывает, что видимая строка состояния должна быть создана в нижней части окна фрейма. Примените любое сочетание стилей элемента управления "строка состояния", перечисленных в [окне Стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles) и [CDialogBar:: Create](../../mfc/reference/cdialogbar-class.md#create). Однако этот параметр всегда должен включать стили WS_CHILD и WS_VISIBLE.

*nID*<br/>
Идентификатор дочернего окна в строке состояния.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция также задает исходный шрифт и задает для высоты строки состояния значение по умолчанию.

Используйте `CreateEx`вместо [CREATE](#create), когда определенные стили должны присутствовать во время создания встроенного элемента управления "строка состояния". Например, задайте для *двктрлстиле* значение SBT_TOOLTIPS, чтобы отобразить подсказки в объекте строки состояния.

##  <a name="cstatusbar"></a>CStatusBar:: CStatusBar

`CStatusBar` Конструирует объект, при необходимости создает шрифт строки состояния по умолчанию и устанавливает характеристики шрифта в значения по умолчанию.

```
CStatusBar();
```

##  <a name="drawitem"></a>CStatusBar::D Равитем

Эта функция-член вызывается платформой при изменении визуального аспекта рисуемой владельцем строки состояния.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*лпдравитемструкт*<br/>
Указатель на структуру [дравитемструкт](/windows/win32/api/winuser/ns-winuser-drawitemstruct) , содержащую сведения о типе требуемой прорисовки.

### <a name="remarks"></a>Примечания

`itemAction` Элемент`DRAWITEMSTRUCT` структуры определяет выполняемое действие рисования. Переопределите эту функцию-член, чтобы реализовать Рисование для объекта `CStatusBar` , рисуемого владельцем. Приложение должно восстановить все объекты интерфейса графических устройств (GDI), выбранные для контекста вывода, указанного в *лпдравитемструкт* перед завершением этой функции-члена.

##  <a name="getitemid"></a>CStatusBar:: Жетитемид

Возвращает идентификатор индикатора, заданного параметром *ниндекс*.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс индикатора, идентификатор которого необходимо получить.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор индикатора, заданного параметром *ниндекс*.

##  <a name="getitemrect"></a>CStatusBar:: Жетитемрект

Копирует координаты индикатора, указанного параметром *ниндекс* , в структуру, на которую указывает *лпрект*.

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс индикатора, координаты прямоугольника которого необходимо получить.

*лпрект*<br/>
Указывает на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) или объект [крект](../../atl-mfc-shared/reference/crect-class.md) , который будет принимать координаты индикатора, указанного параметром *ниндекс*.

### <a name="remarks"></a>Примечания

Координаты задаются в пикселях относительно левого верхнего угла строки состояния.

##  <a name="getpaneinfo"></a>CStatusBar:: Жетпанеинфо

Устанавливает *NID*, *нстиле*и *кксвидс* в соответствии с идентификатором, стилем и шириной панели индикаторов в расположении, заданном *ниндекс*.

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс области, сведения о которой необходимо получить.

*nID*<br/>
Ссылка на значение UINT, заданное ИДЕНТИФИКАТОРом панели.

*нстиле*<br/>
Ссылка на тип UINT, заданный стилем панели.

*кксвидс*<br/>
Ссылка на целое число, для которого задана ширина панели.

##  <a name="getpanestyle"></a>CStatusBar:: Жетпанестиле

Вызовите эту функцию-член, чтобы получить стиль панели строки состояния.

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс области, стиль которой необходимо получить.

### <a name="return-value"></a>Возвращаемое значение

Стиль области строки состояния, заданной параметром *ниндекс*.

### <a name="remarks"></a>Примечания

Стиль панели определяет, как отображается панель.

Список стилей, доступных для строк состояния, см. в разделе [CREATE](#create).

##  <a name="getpanetext"></a>CStatusBar:: Жетпанетекст

Вызовите эту функцию-член, чтобы получить текст, отображаемый на панели строки состояния.

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс области, текст которой необходимо получить.

*rStr*<br/>
Ссылка на объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий текст для извлечения.

### <a name="return-value"></a>Возвращаемое значение

`CString` Объект, содержащий текст панели.

### <a name="remarks"></a>Примечания

Вторая форма этой функции-члена заполняет `CString` объект строкой текста.

##  <a name="getstatusbarctrl"></a>CStatusBar:: Жетстатусбарктрл

Эта функция – член обеспечивает прямой доступ к базовому общему элементу управления.

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Содержит ссылку на объект [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) .

### <a name="remarks"></a>Примечания

Используйте `GetStatusBarCtrl` , чтобы воспользоваться преимуществами функций общего элемента управления "панель состояния Windows" и воспользоваться преимуществами [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) поддержки для настройки строки состояния. Например, с помощью общего элемента управления можно указать стиль, который включает захват изменения размера в строке состояния, или же можно указать стиль, чтобы строка состояния отображалась в верхней части клиентской области родительского окна.

Дополнительные общие сведения об общих элементах управления см. в разделе [Общие элементы управления](/windows/win32/Controls/common-controls-intro) в Windows SDK.

##  <a name="setindicators"></a>CStatusBar:: Сетиндикаторс

Устанавливает идентификатор каждого индикатора в значение, заданное соответствующим элементом массива *лпидаррай*, загружает строковый ресурс, заданный каждым идентификатором, и задает текст индикатора в виде строки.

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Параметры

*лпидаррай*<br/>
Указатель на массив идентификаторов.

*нидкаунт*<br/>
Число элементов в массиве, на которое указывает *лпидаррай*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

##  <a name="setpaneinfo"></a>CStatusBar:: Сетпанеинфо

Задает для указанной панели индикатора новый идентификатор, стиль и ширину.

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс области индикатора, стиль которой должен быть установлен.

*nID*<br/>
Новый идентификатор для панели индикаторов.

*нстиле*<br/>
Новый стиль для панели индикаторов.

*кксвидс*<br/>
Новая ширина панели индикаторов.

### <a name="remarks"></a>Примечания

Поддерживаются следующие стили индикаторов:

- SBPS_NOBORDERS вокруг панели нет трехмерной границы.

- SBPS_POPOUT обратную границу, чтобы текст "выталкивает".

- SBPS_DISABLED не выводить текст.

- SBPS_STRETCH область Stretch для заполнения неиспользуемого пространства. Только одна панель на строку состояния может иметь этот стиль.

- SBPS_NORMAL без растяжения, границ или всплывающего окна.

##  <a name="setpanestyle"></a>CStatusBar:: Сетпанестиле

Вызовите эту функцию-член, чтобы задать стиль панели строки состояния.

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс области, стиль которой должен быть установлен.

*нстиле*<br/>
Стиль области, стиль которой должен быть установлен.

### <a name="remarks"></a>Примечания

Стиль панели определяет, как отображается панель.

Список стилей, доступных для строк состояния, см. в разделе [сетпанеинфо](#setpaneinfo).

##  <a name="setpanetext"></a>CStatusBar:: Сетпанетекст

Вызовите эту функцию члена, чтобы установить текст панели в строку, на которую указывает *лпсзневтекст*.

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Индекс области, текст которой необходимо задать.

*лпсзневтекст*<br/>
Указатель на текст новой области.

*бупдате*<br/>
Если значение — TRUE, панель становится недействительной после установки текста.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

После вызова `SetPaneText`необходимо добавить обработчик обновлений пользовательского интерфейса, чтобы отобразить новый текст в строке состояния.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>См. также

[Пример CTRLBARS в MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример DLGCBR32 для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)
