---
title: Класс Кпанедиалог
ms.date: 11/04/2016
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
ms.openlocfilehash: e7ff55e37194d0fa405925e4b3895428cfcaf9eb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502982"
---
# <a name="cpanedialog-class"></a>Класс Кпанедиалог

`CPaneDialog` Класс поддерживает немодальное, закрепляемое диалоговое окно.

## <a name="syntax"></a>Синтаксис

```
class CPaneDialog : public CDockablePane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|`CPaneDialog::CPaneDialog`|Конструктор по умолчанию.|
|`CPaneDialog::~CPaneDialog`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кпанедиалог:: Create](#create)|Создает Закрепляемое диалоговое окно и прикрепляет его к `CPaneDialog` объекту.|
|`CPaneDialog::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CPaneDialog::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Обрабатывает сообщение [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) . (Переопределяется `CBasePane::HandleInitDialog`.)|
|`CPaneDialog::OnEraseBkgnd`|Обрабатывает сообщение [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) . (Переопределяет [CWnd:: онерасебкгнд](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|
|`CPaneDialog::OnLButtonDblClk`|Обрабатывает сообщение [WM_LBUTTONDBLCLK](/windows/win32/inputdev/wm-lbuttondblclk) . (Переопределяет [CWnd:: онлбуттондблклк](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|Обрабатывает сообщение [WM_LBUTTONDOWN](/windows/win32/inputdev/wm-lbuttondown) . (Переопределяет [CWnd:: онлбуттондовн](../../mfc/reference/cwnd-class.md#onlbuttondown).)|
|`CPaneDialog::OnUpdateCmdUI`|Вызывается платформой для обновления окна диалогового окно. (Переопределяет [CDockablePane:: онупдатекмдуи](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|Обрабатывает сообщение [WM_WINDOWPOSCHANGING](/windows/win32/winmsg/wm-windowposchanging) . (Переопределяет [CWnd:: онвиндовпосчангинг](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Задает шаблон для диалогового окна, который является контейнером элемента управления OLE.|

## <a name="remarks"></a>Примечания

`CPaneDialog` Создайте объект в два этапа. Сначала создайте объект в коде. Во вторых, вызовите метод [кпанедиалог:: Create](#create). Необходимо указать допустимое имя шаблона ресурса или идентификатор шаблона и передать указатель родительскому окну. В противном случае процесс создания завершится ошибкой. В диалоговом окне необходимо указать стиль WS_CHILD и WS_VISIBLE. Рекомендуется также указать стили WS_CLIPCHILDREN и WS_CLIPSIBLINGS. Дополнительные сведения см. в разделе [стили окон](styles-used-by-mfc.md#window-styles).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[кпанедиалог](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** афкспанедиалог. h

##  <a name="create"></a>Кпанедиалог:: Create

Создает диалоговое окно закрепления и прикрепляет его к `CPaneDialog` объекту.

```
BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID,
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*лпсзвиндовнаме*<br/>
окне Имя диалогового окна "закрепление".

*ппарентвнд*<br/>
окне Указывает на родительское окно.

*бхасгриппер*<br/>
окне Значение TRUE, чтобы создать диалоговое окно закрепления с заголовком (захватом); в противном случае — значение FALSE.

*лпсзтемплатенаме*<br/>
окне Имя шаблона диалогового окна ресурса.

*нстиле*<br/>
окне Стиль Windows.

*nID*<br/>
окне Идентификатор элемента управления.

*нидтемплате*<br/>
окне Идентификатор ресурса шаблона диалогового окна.

*двтаббедстиле*<br/>
окне Стиль окна с вкладками, которое возникает при перетаскивании другой панели элементов управления в заголовок этой панели элементов управления. Значение по умолчанию — AFX_CBRS_REGULAR_TABS. Дополнительные сведения см. в подразделе "Примечания" метода [CBasePane:: креатикс](../../mfc/reference/cbasepane-class.md#createex) .

*двконтролбарстиле*<br/>
окне Дополнительные атрибуты стиля. Значение по умолчанию — AFX_DEFAULT_DOCKING_PANE_STYLE. Дополнительные сведения см. в подразделе "Примечания" метода [CBasePane:: креатикс](../../mfc/reference/cbasepane-class.md#createex) .

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод завершился с ошибкой; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере показано, `Create` как использовать метод `CPaneDialog` в классе. Этот пример является частью [примера размера панели Set](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

##  <a name="handleinitdialog"></a>Кпанедиалог:: Хандлеинитдиалог

Обрабатывает сообщение [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) .

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*wParam*<br/>
окне Обработчик для элемента управления, который должен получать фокус клавиатуры по умолчанию.

*lParam*<br/>
окне Задает дополнительные данные инициализации.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE. Кроме того, значение TRUE устанавливает фокус клавиатуры на элемент управления, указанный параметром *wParam* ; Значение FALSE предотвращает установку фокуса клавиатуры по умолчанию.

### <a name="remarks"></a>Примечания

Платформа использует этот метод для инициализации элементов управления и внешнего вида диалогового окна. Платформа вызывает этот метод перед отображением диалогового окна.

##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo

Задает шаблон для диалогового окна, который является контейнером элемента управления OLE.

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Параметры

*поккдиалогинфо*<br/>
окне Указатель на шаблон диалогового окна, который используется для создания объекта диалогового окна. Значение этого параметра впоследствии передается в метод [коккманажер:: креатедлгконтролс](../../mfc/reference/coccmanager-class.md#createdlgcontrols) .

### <a name="return-value"></a>Возвращаемое значение

Всегда имеет значение TRUE.

### <a name="remarks"></a>Примечания

Этот метод поддерживает класс [коккманажер](../../mfc/reference/coccmanager-class.md) , который управляет сайтами элементов управления OLE и элементами управления ActiveX. Структура _AFX_OCC_DIALOG_INFO определена в файле заголовка афксокк. h.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)<br/>
[Стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles)
