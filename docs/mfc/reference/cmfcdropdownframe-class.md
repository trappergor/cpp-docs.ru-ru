---
title: Класс CMFCDropDownFrame
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
ms.openlocfilehash: 508b27acd0a2004b1b8f75fde0bddcdf91194948
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752427"
---
# <a name="cmfcdropdownframe-class"></a>Класс CMFCDropDownFrame

Обеспечивает выпадающие функции окна кадра для выпадающих панелей инструментов и выпадающих кнопок панели инструментов.

## <a name="syntax"></a>Синтаксис

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|`CMFCDropDownFrame::CMFCDropDownFrame`|Конструктор по умолчанию.|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCDropDownFrame::Создание](#create)|Создает объект `CMFCDropDownFrame`.|
|`CMFCDropDownFrame::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Извлекает панель родительского меню в выпадающей кадре.|
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Извлекает родительское всплывающее меню кадра выпадения.|
|`CMFCDropDownFrame::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Перемещает выпадающий кадр.|
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Устанавливает, уничтожается ли окно панели инструментов ребенка автоматически.|

### <a name="remarks"></a>Remarks

Данный класс не предназначен для непосредственного использования в коде.

Платформа использует этот класс для обеспечения поведения кадров для классов `CMFCDropDownToolbar` и `CMFCDropDownToolbarButton` классов. Для получения дополнительной информации об этих классах, см [CMFCDropDownToolBar класса](../../mfc/reference/cmfcdropdowntoolbar-class.md) и [CMFCDropDownToolbarButton класса](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).

## <a name="example"></a>Пример

В следующем примере показано, как получить `CMFCDropDownFrame` указатель `CFrameWnd` объекта из класса и как настроить окно панели панели инструментов для автоматического уничтожения окна панели панели выпадения ребенка.

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdropdowntoolbar.h

## <a name="cmfcdropdownframecreate"></a><a name="create"></a>CMFCDropDownFrame::Создание

Создает объект `CMFCDropDownFrame`.

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pWndParent*|(в) Родительское окно выпадающей кадра.|
|*x*|(в) Горизонтальный экран координирует расположение вниз кадра.|
|*Y*|(в) Вертикальный экран координирует расположение вниз кадра.|
|*pWndOriginToolbar*|(в) Панель инструментов, которая имеет кнопки выпадения, которые этот метод использует для заполнения нового объекта кадра.|

### <a name="return-value"></a>Возвращаемое значение

TRUE, если выпадающий кадр был успешно создан; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Этот метод называет базовым [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) метод для создания выпадающего окна кадра с WS_POPUP стилем. Окно кадра выпадающего кадра отображается в указанных координатах экрана. Этот метод не удается, если [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) метод возвращает FALSE.

Класс `CMFCDropDownFrame` создает копию предоставленного `CMFCDropDownToolBar` параметра. Этот метод копирует изображения кнопок и состояния `pWndOriginToolbar` кнопок от параметра к члену `m_pWndOriginToolbar` данных.

## <a name="cmfcdropdownframegetparentmenubar"></a><a name="getparentmenubar"></a>CMFCDropDownFrame::GetParentMenuBar

Извлекает панель родительского меню в выпадающей кадре.

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на панель родительского меню кадра выпадения или NULL, если в кадре нет родительского элемента.

### <a name="remarks"></a>Remarks

Этот метод извлекает панель меню родительского из кнопки «Родитель». Этот метод возвращает NULL, если в выпадающем кадре нет родительской кнопки или кнопка родительского меню не имеет родительского меню.

## <a name="cmfcdropdownframegetparentpopupmenu"></a><a name="getparentpopupmenu"></a>CMFCDropDownFrame::GetParentPopupMenu

Извлекает родительское всплывающее меню кадра выпадения.

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на родительское выпадающее меню кадра выпадения или NULL, если в кадре нет родительского элемента.

### <a name="remarks"></a>Remarks

Этот метод извлекает родительское меню из кнопки «Родитель». Этот метод возвращает NULL, если в выпадающем кадре нет родительской кнопки или кнопка родительского элемента не имеет родительского меню.

## <a name="cmfcdropdownframerecalclayout"></a><a name="recalclayout"></a>CMFCDropDownFrame::RecalcLayout

Перемещает выпадающий кадр.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*bNotify*|[in] Не используется.|

### <a name="remarks"></a>Remarks

Рамочная система вызывает этот метод при создании кадра выпадения или повторного размера родительского окна. Этот метод вычисляет положение и размер выпадающих кадров, используя положение и размер родительского окна.

## <a name="cmfcdropdownframesetautodestroy"></a><a name="setautodestroy"></a>CMFCDropDownFrame::SetAutoDestroy

Устанавливает, уничтожается ли окно панели инструментов ребенка автоматически.

```cpp
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*bAutoDestroy*<br/>
(в) TRUE для автоматического уничтожения связанного окна панели инструментов; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Если *bAutoDestroy* является правдой, то `CMFCDropDownFrame` деструктор разрушает связанное окно панели инструментов. Значение по умолчанию — TRUE.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CmFCDropDownToolbarButton класс](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
