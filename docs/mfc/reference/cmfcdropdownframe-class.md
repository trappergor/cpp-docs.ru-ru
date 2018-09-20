---
title: Класс CMFCDropDownFrame | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ae1b3dfdd4b5d2160b154a99f76a505a8fb82cf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428048"
---
# <a name="cmfcdropdownframe-class"></a>Класс CMFCDropDownFrame

Предоставляет функциональные возможности окна фрейма раскрывающегося списка в раскрывающемся списке панели инструментов и кнопки панели инструментов с раскрывающимся.

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
|[CMFCDropDownFrame::Create](#create)|Создает объект `CMFCDropDownFrame`.|
|`CMFCDropDownFrame::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|Извлекает меню родительского фрейма раскрывающегося списка.|
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|Извлекает родительский во всплывающем меню фрейма раскрывающегося списка.|
|`CMFCDropDownFrame::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|Кадр изменяет положение в раскрывающемся списке.|
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|Задает ли автоматически уничтожается дочернее окно раскрывающегося списка на панели инструментов.|

### <a name="remarks"></a>Примечания

Этот класс не предназначен для использования непосредственно из программного кода.

Инфраструктура использует этот класс для предоставления поведение фрейма для `CMFCDropDownToolbar` и `CMFCDropDownToolbarButton` классы. Дополнительные сведения об этих классах см. в разделе [класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md) и [класс CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).

## <a name="example"></a>Пример

Следующий пример демонстрирует, как получить указатель на `CMFCDropDownFrame` объекта из `CFrameWnd` класс и как задать дочерние окно раскрывающегося списка на панели инструментов, чтобы быть автоматически уничтожена.

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

##  <a name="create"></a>  CMFCDropDownFrame::Create

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
|*pWndParent*|[in] Родительское окно фрейма раскрывающегося списка.|
|*x*|[in] Горизонтальная координата экрана для расположения кадра в раскрывающемся списке.|
|*y*|[in] Вертикальная координата экрана для расположения кадра в раскрывающемся списке.|
|*pWndOriginToolbar*|[in] Панель инструментов, расположены кнопки раскрывающегося списка, этот метод использует для заполнения нового объекта кадра раскрывающегося списка.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кадр раскрывающегося списка был успешно создан; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывает базовый [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) метод для создания окна фрейма раскрывающегося списка со стилем WS_POPUP. По указанным координатам экрана появится окно раскрывающегося списка кадров. Этот метод завершается ошибкой, если [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) метод возвращает значение FALSE.

`CMFCDropDownFrame` Класс создает копию предоставленного `CMFCDropDownToolBar` параметра. Этот метод копирует изображения кнопок и состояния кнопки из `pWndOriginToolbar` параметр `m_pWndOriginToolbar` элемент данных.

##  <a name="getparentmenubar"></a>  CMFCDropDownFrame::GetParentMenuBar

Извлекает меню родительского фрейма раскрывающегося списка.

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на строку меню родительского фрейма раскрывающегося списка, или значение NULL, если кадр не имеет родительского элемента.

### <a name="remarks"></a>Примечания

Этот метод извлекает родительского меню с помощью кнопки родительского. Этот метод возвращает значение NULL, если кадр раскрывающегося списка имеет никакая кнопка мыши родительский или кнопки родительского нет родительской строки меню.

##  <a name="getparentpopupmenu"></a>  CMFCDropDownFrame::GetParentPopupMenu

Извлекает родительский во всплывающем меню фрейма раскрывающегося списка.

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на стрелку раскрывающегося меню родительского фрейма раскрывающегося списка, или значение NULL, если кадр не имеет родительского элемента.

### <a name="remarks"></a>Примечания

Этот метод извлекает родительского меню с помощью кнопки родительского. Этот метод возвращает значение NULL, если кадр раскрывающегося списка никакая кнопка мыши родительский или родительского кнопка имеет нет родительского меню.

##  <a name="recalclayout"></a>  CMFCDropDownFrame::RecalcLayout

Кадр изменяет положение в раскрывающемся списке.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*bNotify*|[in] Не используется.|

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой при создания фрейма раскрывающегося списка или изменении размера родительского окна. Этот метод вычисляет положение и размер раскрывающегося списка с помощью положение и размер родительского окна.

##  <a name="setautodestroy"></a>  CMFCDropDownFrame::SetAutoDestroy

Задает ли автоматически уничтожается дочернее окно раскрывающегося списка на панели инструментов.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*bAutoDestroy*<br/>
[in] Значение TRUE, чтобы автоматически уничтожить окно соответствующей раскрывающемся списке панели инструментов; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если *bAutoDestroy* имеет значение TRUE, то `CMFCDropDownFrame` деструктор уничтожает окно соответствующей панели инструментов в раскрывающемся списке. Значение по умолчанию — TRUE.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[Класс CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
