---
title: CReBar-класс
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
ms.openlocfilehash: 4216898e85ebbec748598e10ebb31ce5510f7908
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267788"
---
# <a name="crebar-class"></a>CReBar-класс

Панель элементов управления, которая предоставляет макет, сохраняемость и сведения о состоянии для элементов управления главной панели.

## <a name="syntax"></a>Синтаксис

```
class CReBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CReBar::AddBar](#addbar)|Добавляет полосу элемент управления главной панели.|
|[CReBar::Create](#create)|Создает элемент управления "Главная панель" и присоединяет его к `CReBar` объекта.|
|[CReBar::GetReBarCtrl](#getrebarctrl)|Обеспечивает прямой доступ к базовой общего элемента управления.|

## <a name="remarks"></a>Примечания

Объект "Главная панель" может содержать множество дочерних окон, обычно другие элементы управления, включая поля ввода, панелей инструментов и списки. Объект "Главная панель" можно отобразить его дочерних окон на указанном точечном рисунке. Приложение может автоматически изменить размер главной панели, или пользователя можно вручную изменить размер главной панели, щелкните и перетащите его полосу захвата.

![Пример меню rebarmenu](../../mfc/reference/media/vc4sc61.gif "пример меню rebarmenu")

## <a name="rebar-control"></a>Главной панели управления

Объект "Главная панель" ведет себя аналогично объект панели инструментов. Элемент управления главной панели использует механизм щелкните и перетащите для изменения размера в своей зоне. Элемент управления "Главная панель" может содержать один или несколько групп, с каждой зоны, наличие любое сочетание полосу захвата, битовая карта, текстовую метку и дочернего окна. Тем не менее лентами, не может содержать более одного дочернего окна.

`CReBar` использует [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) класс, чтобы обеспечить его реализации. Можно получить доступ к этим элементом управления "Главная панель" посредством [GetReBarCtrl](#getrebarctrl) Чтобы воспользоваться преимуществами возможности настройки элемента управления. Дополнительные сведения об элементах управления главной панели, см. в разделе `CReBarCtrl`. Дополнительные сведения об использовании элементов управления "Главная панель" см. в разделе [использование CReBarCtrl](../../mfc/using-crebarctrl.md).

> [!CAUTION]
>  "Главная панель" и "Главная панель" объекты элементов управления не поддерживают панель закрепления элементов управления MFC. Если `CRebar::EnableDocking` вызове будет утверждать приложения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

##  <a name="addbar"></a>  CReBar::AddBar

Вызывайте эту функцию элемент, добавляемый аппаратного контроллера управления главной панели.

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

*pBar*<br/>
Указатель на `CWnd` объект, являющийся дочернего окна для вставки в главной панели. Упоминаемый объект должен иметь WS_CHILD.

*lpszText*<br/>
Указатель на строку, содержащую текст, появляющийся на главной панели. Значение NULL по умолчанию. Текст, содержащийся в *lpszText* не является частью дочернее окно; он ведет на сам главной панели.

*pbmp*<br/>
Указатель на `CBitmap` объект для отображения на заднем плане главной панели. Значение NULL по умолчанию.

*dwStyle*<br/>
DWORD, содержащее стиль для применения к главной панели. См. в разделе `fStyle` функции описание структуры Win32 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) полный список стилей аппаратного контроллера управления.

*clrFore*<br/>
Значение COLORREF, представляющий цвет переднего плана для главной панели.

*clrBack*<br/>
Значение COLORREF, представляющее цвет фона элемента главной панели.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

##  <a name="create"></a>  CReBar::Create

Вызывайте эту функцию член, чтобы создать элемент управления главной панели.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на `CWnd` объекта, окно которого Windows является родительским для объекта строки состояния. Обычно фрейма окна.

*dwCtrlStyle*<br/>
Стиль элемента управления "Главная панель". По умолчанию RBS_BANDBORDERS, который отображает узких строк для разделения смежные полосами в элементе управления "Главная панель". См. в разделе [стили элемента управления главной панели](/windows/desktop/Controls/rebar-control-styles) в пакете SDK Windows для получения списка стилей.

*dwStyle*<br/>
Стили окна "Главная панель".

*nID*<br/>
Идентификатор элемента главной панели дочернего окна.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

  См. в примере [CReBar::AddBar](#addbar).

##  <a name="getrebarctrl"></a>  CReBar::GetReBarCtrl

Эта функция-член обеспечивает прямой доступ к базовой общего элемента управления.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылку на [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) объекта.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию члена, чтобы воспользоваться преимуществами функции Windows "Главная панель" стандартного элемента управления в настройки вашей главной панели. При вызове `GetReBarCtrl`, он возвращает ссылочного объекта к `CReBarCtrl` объекта, поэтому вы можете использовать любой набор функций-членов.

Дополнительные сведения об использовании `CReBarCtrl` для настройки на главной панели, см. в разделе [использование CReBarCtrl](../../mfc/using-crebarctrl.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC MFCIE](../../visual-cpp-samples.md)<br/>
[Класс CControlBar](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
