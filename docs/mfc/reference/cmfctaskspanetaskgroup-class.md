---
title: Класс CMFCTasksPaneTaskGroup
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
ms.openlocfilehash: a28f00fb732727ec1334946a9e752679307cd3a0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295231"
---
# <a name="cmfctaskspanetaskgroup-class"></a>Класс CMFCTasksPaneTaskGroup

`CMFCTasksPaneTaskGroup` Класс — это вспомогательный класс, используемый [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) элемента управления. Объекты типа `CMFCTasksPaneTaskGroup` представляют *группу задач*. Группа задач — это список элементов, отображаемых структурой в отдельном поле с кнопкой "Свернуть". Поле может иметь необязательный заголовок (имя группы). Если группа свернута, список задач не отображается.

## <a name="syntax"></a>Синтаксис

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Создает объект `CMFCTasksPaneTaskGroup`.|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Определяет, какие данные специальных возможностей для текущей группы задач.|

### <a name="data-members"></a>Элементы данных

|name|Описание:|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Определяет, выровнены ли группа задач в нижней части элемента управления области задач.|
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Определяет, свернута ли группа задач.|
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Определяет, является ли группа задач *специальные.* Платформа отображает специальные заголовки другим цветом.|
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|Содержит внутренний список задач.|
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Указывает ограничивающий прямоугольник заголовка группы.|
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Указывает ограничивающий прямоугольник группы.|
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Задает имя группы.|

## <a name="remarks"></a>Примечания

На следующем рисунке показан группу расширенные задачи:

![Развернутая группа задач](../../mfc/reference/media/nexttaskgrpexpand.png "Развернутая группа задач")

На следующем рисунке показан свернутая группа задач:

![Группа задач Collapsed](../../mfc/reference/media/nexttaskgrpcollapse.png "свернутые группы задач")

На следующем рисунке показан группа задач без заголовка:

![Группа задач без заголовка](../../mfc/reference/media/nexttaskgrpnocapt.png "группа задач без заголовка")

Ниже показаны две группы задач. Первая группа задач, задав помечается как специальные `m_bIsSpecial` флаг значение TRUE, а вторая группа задач не является особенным. Обратите внимание, что заголовок для первой группы задач темнее, чем вторая группа задач:

![Специальная группа задач](../../mfc/reference/media/nexttaskgrpspecial.png "специальная группа задач")

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxTasksPane.h

##  <a name="cmfctaskspanetaskgroup"></a>  CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup

Создает объект `CMFCTasksPaneTaskGroup`.

```
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,
    BOOL bIsBottom,
    BOOL bIsSpecial=FALSE,
    BOOL bIsCollapsed=FALSE,
    CMFCTasksPanePropertyPage* pPage=NULL,
    HICON hIcon=NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указывает имя группы в заголовке группы.

*bIsBottom*<br/>
Указывает, выравнивается ли группы в нижнюю часть элемента управления области задач.

*bIsSpecial*<br/>
Указывает, является ли группа используется в качестве *специальные* , и таким образом, является ли название группы заполняется другим цветом.

*bIsCollapsed*<br/>
Определяет, свернута ли группа.

*Физ_страница*<br/>
Указывает страницу свойств, к которой принадлежит эта группа задач.

*hIcon*<br/>
Указывает значок, отображаемый в заголовке группы.

### <a name="remarks"></a>Примечания

##  <a name="m_bisbottom"></a>  CMFCTasksPaneTaskGroup::m_bIsBottom

Определяет, выровнены ли группа задач в нижней части элемента управления области задач.

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>Примечания

Только одна группа может быть выровнен по нижней части элемента управления области задач. Последнее необходимо добавить эту группу задач. Дополнительные сведения см. в разделе [CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).

##  <a name="m_biscollapsed"></a>  CMFCTasksPaneTaskGroup::m_bIsCollapsed

Определяет, свернута ли группа задач.

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>Примечания

Можно включить или отключить возможность свернуть группы в области задач путем вызова [CMFCTasksPane::EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).

##  <a name="m_bisspecial"></a>  CMFCTasksPaneTaskGroup::m_bIsSpecial

Определяет, является ли группа задач *специальные* и ли заголовок для группы «специальная задача» должны идентифицироваться по другим цветом.

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>Примечания

Если приложение использует визуальной темы Windows XP и `m_bIsSpecial` имеет значение FALSE, платформа вызывает `DrawThemeBackground` с флагом EBP_NORMALGROUPBACKGROUND. Если `m_bIsSpecial` имеет значение TRUE, платформа вызывает `DrawThemeBackground` с флагом EBP_SPECIALGROUPBACKGROUND.

##  <a name="m_lsttasks"></a>  CMFCTasksPaneTaskGroup::m_lstTasks

Содержит внутренний список задач.

```
CObList m_lstTasks;
```

### <a name="remarks"></a>Примечания

Для заполнения этого списка, вызовите [CMFCTasksPane::AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask).

##  <a name="m_rect"></a>  CMFCTasksPaneTaskGroup::m_rect

Указывает ограничивающий прямоугольник заголовка группы.

```
CRect m_rect;
```

### <a name="remarks"></a>Примечания

Это значение вычисляется автоматически платформой.

##  <a name="m_rectgroup"></a>  CMFCTasksPaneTaskGroup::m_rectGroup

Указывает ограничивающий прямоугольник группы.

```
CRect m_rectGroup;
```

### <a name="remarks"></a>Примечания

Это значение вычисляется автоматически платформой.

##  <a name="m_strname"></a>  CMFCTasksPaneTaskGroup::m_strName

Задает имя группы.

```
CString m_strName;
```

### <a name="remarks"></a>Примечания

Если это значение не указано, отображается название группы и их нельзя свернуть группу.

##  <a name="setaccdata"></a>  CMFCTasksPaneTaskGroup::SetACCData

Определяет, какие данные специальных возможностей для текущей группы задач.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*pParent*<br/>
[in] Представляет родительское окно текущей группы задач.

*data*<br/>
[out] Объект типа `CAccessibilityData` заполняется данные специальных возможностей текущей группы задач.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если *данных* параметр был успешно заполнен данные специальных возможностей текущей группы задач; в противном случае — значение FALSE.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)<br/>
[Класс CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)
