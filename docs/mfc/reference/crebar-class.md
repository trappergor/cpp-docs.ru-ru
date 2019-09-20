---
title: Класс Кребар
ms.date: 11/19/2018
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
ms.openlocfilehash: 434232e8f99bf914b00379db53d4b4a37d24fe36
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502785"
---
# <a name="crebar-class"></a>Класс Кребар

Панель элементов управления, которая предоставляет макет, сохраняемость и сведения о состоянии для элементов управления главной панели.

## <a name="syntax"></a>Синтаксис

```
class CReBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кребар:: Аддбар](#addbar)|Добавляет полосу к главной панели.|
|[Кребар:: Create](#create)|Создает элемент управления "Главная панель" и прикрепляет `CReBar` его к объекту.|
|[Кребар:: Жетребарктрл](#getrebarctrl)|Разрешает прямой доступ к базовому общему элементу управления.|

## <a name="remarks"></a>Примечания

Объект главной панели может содержать различные дочерние окна, обычно другие элементы управления, включая поля редактирования, панели инструментов и списки. Объект главной панели может отображать свои дочерние окна по заданному точечному рисунку. Приложение может автоматически изменять размер главной панели, или пользователь может вручную изменить размер главной панели, щелкнув или перетащив панель захвата.

![Пример ребармену](../../mfc/reference/media/vc4sc61.gif "Пример ребармену")

## <a name="rebar-control"></a>Элемент управления главной панели

Объект главной панели ведет себя аналогично объекту ToolBar. Для изменения размеров его полос Главная панель использует механизм щелчка и перетаскивания. Элемент управления "Главная панель" может содержать одну или несколько полос, каждая из которых имеет любую комбинацию полосы захвата, точечного рисунка, метки текста и дочернего окна. Однако полосы не могут содержать более одного дочернего окна.

`CReBar`использует класс [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) для предоставления его реализации. Чтобы воспользоваться возможностями настройки элемента управления, можно получить доступ к элементу управления главной панели через [жетребарктрл](#getrebarctrl) . Дополнительные сведения о главных элементах управления см `CReBarCtrl`. в разделе. Дополнительные сведения об использовании элементов управления "Главная панель" см. [в разделе using CReBarCtrl](../../mfc/using-crebarctrl.md).

> [!CAUTION]
>  Управляющие объекты главной панели и главной панели не поддерживают закрепление панели элементов управления MFC. Если `CRebar::EnableDocking` вызывается, приложение будет утверждать.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>Требования

**Заголовок:** афксекст. h

##  <a name="addbar"></a>Кребар:: Аддбар

Вызовите эту функцию-член, чтобы добавить полосу к главной панели.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Параметры

*пбар*<br/>
Указатель на `CWnd` объект, который является дочерним окном для вставки в главную панель. Объект, на который указывает ссылка, должен иметь WS_CHILD.

*lpszText*<br/>
Указатель на строку, содержащую текст, отображаемый в главной панели. По умолчанию имеет значение NULL. Текст, содержащийся в *лпсзтекст* , не является частью дочернего окна; Он находится в самой главной панели.

*pbmp*<br/>
Указатель на `CBitmap` объект, отображаемый на фоне главной панели. По умолчанию имеет значение NULL.

*двстиле*<br/>
Значение типа DWORD, содержащее стиль, применяемый к главной панели. Полный список стилей диапазонов см. в описании функции `fStyle` в разделе Структура Win32 [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow).

*клрфоре*<br/>
Значение COLORREF, представляющее цвет переднего плана главной панели.

*клрбакк*<br/>
Значение COLORREF, представляющее цвет фона главной панели.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

##  <a name="create"></a>Кребар:: Create

Вызовите эту функцию-член для создания главной панели.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Параметры

*ппарентвнд*<br/>
Указатель на `CWnd` объект, окно окна которого является родительским для строки состояния. Обычно это окно фрейма.

*двктрлстиле*<br/>
Стиль элемента управления главной панели. По умолчанию RBS_BANDBORDERS, отображающий узкие строки для разделения смежных полос в элементе управления "Главная панель". Список стилей см. в разделе [стили элементов управления главной панели](/windows/win32/Controls/rebar-control-styles) в Windows SDK.

*двстиле*<br/>
Стили окна главной панели.

*nID*<br/>
Идентификатор дочернего окна главной панели.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. пример для [кребар:: аддбар](#addbar).

##  <a name="getrebarctrl"></a>Кребар:: Жетребарктрл

Эта функция – член обеспечивает прямой доступ к базовому общему элементу управления.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) .

### <a name="remarks"></a>Примечания

Вызовите эту функцию члена, чтобы воспользоваться возможностями стандартного элемента управления "Главная панель Windows" в настройке главной панели. При вызове `GetReBarCtrl`он возвращает объект ссылки `CReBarCtrl` на объект, чтобы можно было использовать любой набор функций-членов.

Дополнительные сведения об использовании `CReBarCtrl` для настройки главной панели см. в разделе [Использование CReBarCtrl](../../mfc/using-crebarctrl.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>См. также

[Пример MFCIE для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
