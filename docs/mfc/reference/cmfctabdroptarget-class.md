---
title: Класс CMFCTabDropTarget
ms.date: 11/04/2016
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
ms.openlocfilehash: 83432fdb90fe28214fb1faaf843556deb2f44750
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367358"
---
# <a name="cmfctabdroptarget-class"></a>Класс CMFCTabDropTarget

Обеспечивает механизм связи между управлением вкладками и библиотеками OLE.

## <a name="syntax"></a>Синтаксис

```
class CMFCTabDropTarget : public COleDropTarget
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|||
|-|-|
|Имя|Описание|
|`CMFCTabDropTarget::CMFCTabDropTarget`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|||
|-|-|
|Имя|Описание|
|[CMFCTabdroptarget::OndragEnter](#ondragenter)|Вызывается фректовом, когда пользователь перетаскивает объект в окно вкладки. (Переопределяет [ColedropTarget::Ondragenter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|
|[CMFCTabDropTarget::OndragLeave](#ondragleave)|Вызывается в фреймворке, когда пользователь перетаскивает объект за окно вкладки с фокусом. (Переопределяет [ColedropTarget::OndragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|
|[CMFCTabdroptarget::Ondragover](#ondragover)|Вызывается по системе, когда пользователь перетаскивает объект на окно вкладки, которое имеет фокус. (Переопределяет [Coledroptarget::Ondragover](../../mfc/reference/coledroptarget-class.md#ondragover).)|
|[CMFCTabDroptarget::OndropEx](#ondropex)|Вызывается по системе, когда пользователь выпускает кнопку мыши в конце операции перетаскивания. (Переопределяет [ColedropTarget::Ondropex](../../mfc/reference/coledroptarget-class.md#ondropex).)|
|[CMFCTabDropTarget:Регистрация](#register)|Регистрирует элемент управления как элемент, который может быть целью операции перетаскивания OLE.|

### <a name="remarks"></a>Remarks

Этот класс обеспечивает поддержку перетаскивания и падения `CMFCBaseTabCtrl` класса. Если приложение инициализирует библиотеки OLE с помощью `CMFCBaseTabCtrl` функции [AfxOleInit,](ole-initialization.md#afxoleinit) объекты регистрируются для операций перетаскивания и падения.

Класс `CMFCTabDropTarget` расширяет свой базовый класс, делая вкладку, которая находится под курсором, когда операция перетаскивания происходит активной. Для получения дополнительной информации об операциях перетаскивания, [см.](../../mfc/drag-and-drop-ole.md)

## <a name="example"></a>Пример

В этом примере демонстрируется создание объекта `CMFCTabDropTarget` и использование его метода `Register`.

[!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleDropTarget](../../mfc/reference/coledroptarget-class.md)

[CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxbasetabctrl.h

## <a name="cmfctabdroptargetondragenter"></a><a name="ondragenter"></a>CMFCTabdroptarget::OndragEnter

Вызывается фректовом, когда пользователь перетаскивает объект в окно вкладки.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pWnd*|[in] Не используется.|
|*pDataObject*|(в) Указатель на объект, который перетаскивает пользователь.|
|*dwKeyState*|(в) Содержит состояние ключей модификатора. Это сочетание любого числа: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.|
|*Точки*|(в) Расположение курсора в координатах клиента.|

### <a name="return-value"></a>Возвращаемое значение

Эффект, который приводит, если падение происходит в месте, указанном по *точке.* Это может быть один или несколько из следующих:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Remarks

Этот метод возвращает DROPEFFECT_NONE, если платформа панели инструментов не находится в режиме настройки или формат данных Clipboard недоступен. В противном случае он `CMFCBaseTabCtrl::OnDragEnter` возвращает результат вызова с предоставленными параметрами.

Для получения дополнительной информации о режиме [настройки, см. CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Для получения дополнительной информации о форматах данных Clipboard, [см. COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

## <a name="cmfctabdroptargetondragleave"></a><a name="ondragleave"></a>CMFCTabDropTarget::OndragLeave

Вызывается в фреймворке, когда пользователь перетаскивает объект за окно вкладки с фокусом.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pWnd*|[in] Не используется.|

### <a name="remarks"></a>Remarks

Этот метод `CMFCBaseTabCtrl::OnDragLeave` вызывает метод для выполнения операции перетаскивания.

## <a name="cmfctabdroptargetondragover"></a><a name="ondragover"></a>CMFCTabdroptarget::Ondragover

Вызывается по системе, когда пользователь перетаскивает объект на окно вкладки, которое имеет фокус.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pWnd*|[in] Не используется.|
|*pDataObject*|(в) Указатель на объект, который перетаскивает пользователь.|
|*dwKeyState*|(в) Содержит состояние ключей модификатора. Это сочетание любого числа: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.|
|*Точки*|(в) Расположение указателя мыши в координатах клиента.|

### <a name="return-value"></a>Возвращаемое значение

Эффект, который приводит, если падение происходит в месте, указанном по *точке.* Это может быть один или несколько из следующих:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Remarks

Этот метод делает вкладку, которая находится под курсором, когда операция перетаскивания происходит активно. Он возвращает DROPEFFECT_NONE, если платформа панели инструментов не находится в режиме настройки или формат данных Clipboard недоступен. В противном случае он `CMFCBaseTabCtrl::OnDragOver` возвращает результат вызова с предоставленными параметрами.

Для получения дополнительной информации о режиме [настройки, см. CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Для получения дополнительной информации о форматах данных Clipboard, [см. COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

## <a name="cmfctabdroptargetondropex"></a><a name="ondropex"></a>CMFCTabDroptarget::OndropEx

Вызывается по системе, когда пользователь выпускает кнопку мыши в конце операции перетаскивания.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pWnd*|[in] Не используется.|
|*pDataObject*|(в) Указатель на объект, который перетаскивает пользователь.|
|*dropEffect*|(в) Операция сброса по умолчанию.|
|*dropList*|[in] Не используется.|
|*Точки*|(в) Расположение указателя мыши в координатах клиента.|

### <a name="return-value"></a>Возвращаемое значение

В результате эффект падения. Это может быть один или несколько из следующих:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Remarks

Этот метод `CMFCBaseTabCtrl::OnDrop` вызывает, если платформа панели инструментов находится в режиме настройки и доступен формат данных Clipboard. Если вызов `CMFCBaseTabCtrl::OnDrop` возвращает ненулевое значение, этот метод возвращает эффект падения по умолчанию, указанный *dropEffect.* В противном случае этот метод возвращается DROPEFFECT_NONE. Для получения дополнительной информации о эффектах падения, [см. ColeDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).

Для получения дополнительной информации о режиме [настройки, см. CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Для получения дополнительной информации о форматах данных Clipboard, [см. COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

## <a name="cmfctabdroptargetregister"></a><a name="register"></a>CMFCTabDropTarget:Регистрация

Регистрирует элемент управления как элемент, который может быть целью операции перетаскивания OLE.

```
BOOL Register(CMFCBaseTabCtrl *pOwner);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pOwner*|(в) Контроль вкладок для регистрации в качестве цели падения.|

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если регистрация была успешной; в противном случае 0.

### <a name="remarks"></a>Remarks

Этот метод вызывает [COleDropTarget::Регистрация](../../mfc/reference/coledroptarget-class.md#register) для регистрации элемента управления для операций перетаскивания и падения.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Перетаскивание OLE](../../mfc/drag-and-drop-ole.md)
