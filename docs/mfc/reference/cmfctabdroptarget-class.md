---
title: Класс CMFCTabDropTarget | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca9b67737933ceeb59861234759aa2652b6b985e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057456"
---
# <a name="cmfctabdroptarget-class"></a>Класс CMFCTabDropTarget

Предоставляет механизм взаимодействия между вкладок и библиотек OLE.

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
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|Вызывается платформой, когда пользователь перетаскивает объект в окно вкладки. (Переопределяет [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|Вызывается платформой, когда пользователь перетаскивает объект за пределами вкладки окна, имеющий фокус. (Переопределяет [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|
|[CMFCTabDropTarget::OnDragOver](#ondragover)|Вызывается платформой, когда пользователь перетаскивает объект на вкладке окна, имеющий фокус. (Переопределяет [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|
|[CMFCTabDropTarget::OnDropEx](#ondropex)|Вызывается платформой, когда пользователь отпускает кнопку мыши, в конце операции перетаскивания. (Переопределяет [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|
|[CMFCTabDropTarget::Register](#register)|Регистрирует элемент управления, может быть целевым объектом операции перетаскивания и вставки OLE.|

### <a name="remarks"></a>Примечания

Этот класс обеспечивает поддержку перетаскивания и вставки `CMFCBaseTabCtrl` класса. Если приложение инициализирует библиотек OLE, используя [AfxOleInit](ole-initialization.md#afxoleinit) функции `CMFCBaseTabCtrl` объекты регистрируются для операций перетаскивания и вставки.

`CMFCTabDropTarget` Класс расширяет его базового класса, сделав вкладку, находящийся под курсором при активной операции перетаскивания. Дополнительные сведения об операциях перетаскивания и вставки, см. в разделе [Drag and Drop (OLE)](../../mfc/drag-and-drop-ole.md).

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

##  <a name="ondragenter"></a>  CMFCTabDropTarget::OnDragEnter

Вызывается платформой, когда пользователь перетаскивает объект в окно вкладки.

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
|*pDataObject*|[in] Указатель на объект, который пользователь перетаскивает.|
|*dwKeyState*|[in] Содержит состояние клавиши-модификаторы. Это представляет собой сочетание любое количество следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.|
|*точка*|[in] Расположение курсора в координатах клиентской области окна.|

### <a name="return-value"></a>Возвращаемое значение

Эффект, который возникает, если выполняется перетаскивание в расположении, указанном по *точки*. Это может быть один или несколько из следующих:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Примечания

Этот метод возвращает DROPEFFECT_NONE, если framework инструментов не находится в режиме настройки или формата данных буфера недоступен. В противном случае возвращается результат вызова метода `CMFCBaseTabCtrl::OnDragEnter` с указанными параметрами.

Дополнительные сведения о режиме настройки, см. в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах буфера обмена данных, см. в разделе [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

##  <a name="ondragleave"></a>  CMFCTabDropTarget::OnDragLeave

Вызывается платформой, когда пользователь перетаскивает объект за пределами вкладки окна, имеющий фокус.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pWnd*|[in] Не используется.|

### <a name="remarks"></a>Примечания

Этот метод вызывает метод `CMFCBaseTabCtrl::OnDragLeave` метод для выполнения операции перетаскивания.

##  <a name="ondragover"></a>  CMFCTabDropTarget::OnDragOver

Вызывается платформой, когда пользователь перетаскивает объект на вкладке окна, имеющий фокус.

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
|*pDataObject*|[in] Указатель на объект, который пользователь перетаскивает.|
|*dwKeyState*|[in] Содержит состояние клавиши-модификаторы. Это представляет собой сочетание любое количество следующих: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON и MK_RBUTTON.|
|*точка*|[in] Расположение указателя мыши в клиентских координатах.|

### <a name="return-value"></a>Возвращаемое значение

Эффект, который возникает, если выполняется перетаскивание в расположении, указанном по *точки*. Это может быть один или несколько из следующих:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Примечания

Этот метод делает вкладку, находящийся под курсором при активной операции перетаскивания. DROPEFFECT_NONE возвращает в том случае, если framework инструментов не находится в режиме настройки или формата данных буфера недоступен. В противном случае возвращается результат вызова метода `CMFCBaseTabCtrl::OnDragOver` с указанными параметрами.

Дополнительные сведения о режиме настройки, см. в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах буфера обмена данных, см. в разделе [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

##  <a name="ondropex"></a>  CMFCTabDropTarget::OnDropEx

Вызывается платформой, когда пользователь отпускает кнопку мыши, в конце операции перетаскивания.

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
|*pDataObject*|[in] Указатель на объект, который пользователь перетаскивает.|
|*dropEffect*|[in] Операция перетаскивания по умолчанию.|
|*из раскрывающегося списка*|[in] Не используется.|
|*точка*|[in] Расположение указателя мыши в клиентских координатах.|

### <a name="return-value"></a>Возвращаемое значение

Результирующий эффект перетаскивания. Это может быть один или несколько из следующих:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Примечания

Этот метод вызывает метод `CMFCBaseTabCtrl::OnDrop` Если framework панель инструментов находится в режиме настройки, и формата данных буфера обмена. Если вызов `CMFCBaseTabCtrl::OnDrop` возвращает ненулевое значение, этот метод возвращает эффект падающей по умолчанию, определяемое *dropEffect*. В противном случае этот метод возвращает DROPEFFECT_NONE. Дополнительные сведения о эффектов перетаскивания см. в разделе [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).

Дополнительные сведения о режиме настройки, см. в разделе [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Дополнительные сведения о форматах буфера обмена данных, см. в разделе [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

##  <a name="register"></a>  CMFCTabDropTarget::Register

Регистрирует элемент управления, может быть целевым объектом операции перетаскивания и вставки OLE.

```
BOOL Register(CMFCBaseTabCtrl *pOwner);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание|
|*pOwner*|[in] Элемент управления вкладки, регистрируемый в качестве целевого объекта перетаскивания.|

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если регистрация прошла успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) Регистрируемый элемент управления для операций перетаскивания и вставки.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Перетаскивание (OLE)](../../mfc/drag-and-drop-ole.md)

