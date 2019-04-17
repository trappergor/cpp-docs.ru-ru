---
title: Класс CPaneDialog
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
ms.openlocfilehash: c78b8f2cd19e87fa559c3f9bbd24d07543d887c5
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769749"
---
# <a name="cpanedialog-class"></a>Класс CPaneDialog

`CPaneDialog` Класс поддерживает Закрепляемое безрежимное диалоговое окно.

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
|[CPaneDialog::Create](#create)|Создает фиксируемого диалоговое окно и прикрепляет его к `CPaneDialog` объекта.|
|`CPaneDialog::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CPaneDialog::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Обрабатывает [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) сообщения. (Переопределяет `CBasePane::HandleInitDialog`.)|
|`CPaneDialog::OnEraseBkgnd`|Обрабатывает [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd) сообщения. (Переопределяет [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|
|`CPaneDialog::OnLButtonDblClk`|Обрабатывает [WM_LBUTTONDBLCLK](/windows/desktop/inputdev/wm-lbuttondblclk) сообщения. (Переопределяет [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|Обрабатывает [WM_LBUTTONDOWN](/windows/desktop/inputdev/wm-lbuttondown) сообщения. (Переопределяет [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|
|`CPaneDialog::OnUpdateCmdUI`|Вызывается платформой для обновления диалогового окна. (Переопределяет [CDockablePane::OnUpdateCmdUI](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|Обрабатывает [WM_WINDOWPOSCHANGING](/windows/desktop/winmsg/wm-windowposchanging) сообщения. (Переопределяет [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Задает шаблон для диалоговое окно, которое представляет собой контейнер элемента управления OLE.|

## <a name="remarks"></a>Примечания

Создать `CPaneDialog` объекта в два этапа. Во-первых можно создайте объект в коде. Во-вторых, вызовите [CPaneDialog::Create](#create). Необходимо указать допустимый ресурс шаблона или шаблон, идентификатор и передать указатель на родительское окно. В противном случае происходит сбой в процессе создания. Диалоговое окно необходимо указать стиль WS_CHILD и WS_VISIBLE. Рекомендуется также указать WS_CLIPCHILDREN и WS_CLIPSIBLINGS стили. Дополнительные сведения см. в разделе [стили окна](styles-used-by-mfc.md#window-styles).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CPaneDialog](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpanedialog.h

##  <a name="create"></a>  CPaneDialog::Create

Создает диалоговое окно закрепления и присоединяет его к `CPaneDialog` объекта.

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

*lpszWindowName*<br/>
[in] Имя диалогового окна закрепления.

*pParentWnd*<br/>
[in] Указатель на родительское окно.

*bHasGripper*<br/>
[in] Значение TRUE, чтобы создать закрепления диалоговое окно с заголовком (захвата); в противном случае — значение FALSE.

*lpszTemplateName*<br/>
[in] Имя ресурса шаблона диалогового окна.

*nStyle*<br/>
[in] Стиль Windows.

*nID*<br/>
[in] Идентификатор элемента управления.

*nIDTemplate*<br/>
[in] Идентификатор ресурса шаблона диалогового окна.

*dwTabbedStyle*<br/>
[in] Стиль окна с вкладками, что происходит, когда пользователь перетаскивает другую панель элемента управления на заголовок этой панели управления. Значение по умолчанию — AFX_CBRS_REGULAR_TABS. Дополнительные сведения см. в разделе "Примечания" [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) метод.

*dwControlBarStyle*<br/>
[in] Атрибуты дополнительного стиля. Значение по умолчанию — AFX_DEFAULT_DOCKING_PANE_STYLE. Дополнительные сведения см. в разделе "Примечания" [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) метод.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

Следующий пример демонстрирует, как использовать `Create` метод в `CPaneDialog` класса. Этот пример является частью [задать размер области пример](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog

Обрабатывает [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) сообщения.

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*wParam*<br/>
[in] Дескриптор элемента управления, который должен получить фокус клавиатуры по умолчанию.

*lParam*<br/>
[in] Указывает дополнительную инициализацию данных.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE. Кроме того, значение TRUE Задает фокус клавиатуры на элемент управления, заданный *wParam* параметра; Значение FALSE, не позволяет установить фокус клавиатуры по умолчанию.

### <a name="remarks"></a>Примечания

Инфраструктура использует этот метод для инициализации элементов управления и внешний вид диалогового окна. Этот метод вызывается платформой, прежде чем он отображает диалоговое окно.

##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo

Задает шаблон для диалоговое окно, которое представляет собой контейнер элемента управления OLE.

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Параметры

*pOccDialogInfo*<br/>
[in] Указатель на шаблон диалогового окна, используемый для создания объекта поле диалогового окна. Значение этого параметра впоследствии передается в [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) метод.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Этот метод поддерживает [COccManager](../../mfc/reference/coccmanager-class.md) класс, который управляет узлы элемента управления OLE и элементы управления ActiveX. _AFX_OCC_DIALOG_INFO структура определена в файле заголовка afxocc.h.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)<br/>
[Стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles)
