---
title: Класс Кмфкдропдовнфраме
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
ms.openlocfilehash: d99dae9d8e7eca96c736a33621f0b544f1962f0f
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560898"
---
# <a name="cmfcdropdownframe-class"></a>Класс Кмфкдропдовнфраме

Предоставляет функцию раскрывающегося окна рамки для раскрывающихся панелей инструментов и кнопок с раскрывающимися списками.

## <a name="syntax"></a>Синтаксис

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|name|Описание|
|`CMFCDropDownFrame::CMFCDropDownFrame`|Конструктор по умолчанию.|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|name|Описание|
|[Кмфкдропдовнфраме:: Create](#create)|Создает объект `CMFCDropDownFrame`.|
|`CMFCDropDownFrame::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[Кмфкдропдовнфраме:: Жетпарентменубар](#getparentmenubar)|Получает родительскую строку меню раскрывающегося окна.|
|[Кмфкдропдовнфраме:: Жетпарентпопупмену](#getparentpopupmenu)|Извлекает родительское всплывающее меню раскрывающегося окна.|
|`CMFCDropDownFrame::GetThisClass`|Используется платформой для получения указателя на объект [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) , связанный с этим типом класса.|
|[Кмфкдропдовнфраме:: RecalcLayout](#recalclayout)|Перемещает раскрывающийся кадр.|
|[Кмфкдропдовнфраме:: Сетаутодестрой](#setautodestroy)|Задает, будет ли дочернее окно панели инструментов уничтожено автоматически.|

### <a name="remarks"></a>Remarks

Данный класс не предназначен для непосредственного использования в коде.

Платформа использует этот класс для предоставления поведения фрейма `CMFCDropDownToolbar` `CMFCDropDownToolbarButton` классам и. Дополнительные сведения об этих классах см. в разделе [класс кмфкдропдовнтулбар](../../mfc/reference/cmfcdropdowntoolbar-class.md) и [класс кмфкдропдовнтулбарбуттон](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md).

## <a name="example"></a>Пример

В следующем примере показано, как получить указатель на `CMFCDropDownFrame` объект из `CFrameWnd` класса и как задать автоматическое уничтожение дочернего раскрывающегося окна панели инструментов.

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[кмфкдропдовнфраме](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdropdowntoolbar.h

## <a name="cmfcdropdownframecreate"></a><a name="create"></a> Кмфкдропдовнфраме:: Create

Создает объект `CMFCDropDownFrame`.

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>Параметры

*пвндпарент*\
окне Родительское окно раскрывающегося окна.

*x*\
окне Горизонтальная координата экрана для расположения окна вниз.

*&*\
окне Вертикальная координата экрана для расположения вниз.

*пвндоригинтулбар*\
окне Панель инструментов с раскрывающимися кнопками, используемыми этим методом для заполнения нового объекта рамки раскрывающегося списка.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если раскрывающийся список успешно создан; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

Этот метод вызывает базовый метод [кминифрамевнд:: креатикс](../../mfc/reference/cminiframewnd-class.md#createex) для создания раскрывающегося окна с рамкой с WS_POPUP стилем. Раскрывающееся окно с рамками отображается в заданных координатах экрана. Этот метод завершается ошибкой, если метод [кминифрамевнд:: креатикс](../../mfc/reference/cminiframewnd-class.md#createex) возвращает значение false.

`CMFCDropDownFrame`Класс создает копию предоставленного `CMFCDropDownToolBar` параметра. Этот метод копирует изображения кнопок и состояния кнопок из `pWndOriginToolbar` параметра в `m_pWndOriginToolbar` элемент данных.

## <a name="cmfcdropdownframegetparentmenubar"></a><a name="getparentmenubar"></a> Кмфкдропдовнфраме:: Жетпарентменубар

Получает родительскую строку меню раскрывающегося окна.

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на родительскую строку меню раскрывающегося окна или значение NULL, если у фрейма нет родителя.

### <a name="remarks"></a>Remarks

Этот метод извлекает родительскую строку меню из родительской кнопки. Этот метод возвращает значение NULL, если у раскрывающегося окна нет родительской кнопки, или родительская кнопка не имеет родительской строки меню.

## <a name="cmfcdropdownframegetparentpopupmenu"></a><a name="getparentpopupmenu"></a> Кмфкдропдовнфраме:: Жетпарентпопупмену

Извлекает родительское всплывающее меню раскрывающегося окна.

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на родительское раскрывающееся меню раскрывающегося окна или значение NULL, если у фрейма нет родителя.

### <a name="remarks"></a>Remarks

Этот метод извлекает родительское меню из родительской кнопки. Этот метод возвращает значение NULL, если у раскрывающегося окна нет родительской кнопки, или родительская кнопка не имеет родительского меню.

## <a name="cmfcdropdownframerecalclayout"></a><a name="recalclayout"></a> Кмфкдропдовнфраме:: RecalcLayout

Перемещает раскрывающийся кадр.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Параметры

*бнотифи*\
[in] Не используется.

### <a name="remarks"></a>Remarks

Платформа вызывает этот метод при создании раскрывающейся рамки или изменении размера родительского окна. Этот метод вычисляет расположение и размер раскрывающегося фрейма с помощью расположения и размера родительского окна.

## <a name="cmfcdropdownframesetautodestroy"></a><a name="setautodestroy"></a> Кмфкдропдовнфраме:: Сетаутодестрой

Задает, будет ли дочернее окно панели инструментов уничтожено автоматически.

```cpp
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*баутодестрой*<br/>
окне Значение TRUE, чтобы автоматически удалить связанное раскрывающееся окно панели инструментов; в противном случае — значение FALSE.

### <a name="remarks"></a>Remarks

Если *баутодестрой* имеет значение true, `CMFCDropDownFrame` деструктор уничтожает связанное раскрывающееся окно панели инструментов. Значение по умолчанию — TRUE.

## <a name="see-also"></a>См. также

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс Кмфкдропдовнтулбар](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[Класс Кмфкдропдовнтулбарбуттон](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
