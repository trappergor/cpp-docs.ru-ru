---
title: Класс CAnimationGroup
ms.date: 03/27/2019
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
helpviewer_keywords:
- CAnimationGroup [MFC], CAnimationGroup
- CAnimationGroup [MFC], Animate
- CAnimationGroup [MFC], ApplyTransitions
- CAnimationGroup [MFC], FindAnimationObject
- CAnimationGroup [MFC], GetGroupID
- CAnimationGroup [MFC], RemoveKeyframes
- CAnimationGroup [MFC], RemoveTransitions
- CAnimationGroup [MFC], Schedule
- CAnimationGroup [MFC], SetAutodestroyTransitions
- CAnimationGroup [MFC], AddKeyframes
- CAnimationGroup [MFC], AddTransitions
- CAnimationGroup [MFC], CreateTransitions
- CAnimationGroup [MFC], m_bAutoclearTransitions
- CAnimationGroup [MFC], m_bAutodestroyAnimationObjects
- CAnimationGroup [MFC], m_bAutodestroyKeyframes
- CAnimationGroup [MFC], m_lstAnimationObjects
- CAnimationGroup [MFC], m_lstKeyFrames
- CAnimationGroup [MFC], m_pStoryboard
- CAnimationGroup [MFC], m_nGroupID
- CAnimationGroup [MFC], m_pParentController
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
ms.openlocfilehash: 32b2adfee2a36139a11caa12fa98bd240b0732dd
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565991"
---
# <a name="canimationgroup-class"></a>Класс CAnimationGroup

Реализует группу анимации, которая сочетает раскадровку анимации, объекты анимации и переходы для определения анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationGroup;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|Создает группу анимации.|
|[CAnimationGroup:: ~ CAnimationGroup](#_dtorcanimationgroup)|Деструктор Вызывается при уничтожении группу анимации.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CAnimationGroup::Animate](#animate)|Анимирует группу.|
|[CAnimationGroup::ApplyTransitions](#applytransitions)|Применяется переходы к объектам анимации.|
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|Выполняет поиск объекта анимации, содержащую нужную переменную указанным анимации.|
|[CAnimationGroup::GetGroupID](#getgroupid)|Возвращает GroupID.|
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|Удаляет и при необходимости удаляет все опорные кадры, которые принадлежат группе анимации.|
|[CAnimationGroup::RemoveTransitions](#removetransitions)|Удаляет переходы из объекта анимации, которые принадлежат группе анимации.|
|[CAnimationGroup::Schedule](#schedule)|Планирует анимации в указанное время.|
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|Указывает, что переходы уничтожить всех объектов анимации, которые принадлежат группе автоматически.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CAnimationGroup::AddKeyframes](#addkeyframes)|Вспомогательный класс, раскадровки, добавляющий опорные кадры.|
|[CAnimationGroup::AddTransitions](#addtransitions)|Вспомогательный класс, добавляющий переходы к раскадровке.|
|[CAnimationGroup::CreateTransitions](#createtransitions)|Вспомогательный метод, создающий объекты COM перехода.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|Указывает, как очистить переходы из анимации объектов, принадлежащих к группе. Если этот элемент имеет значение TRUE, переходы, удаляются автоматически, при анимации был запланирован. В противном случае необходимо вручную удалить переходы.|
|[CAnimationGroup::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|Указывает, как для уничтожения объектов анимации. Если этот параметр имеет значение TRUE, объекты анимации будут уничтожены автоматически при удалении группы. В противном случае объекты анимации необходимо уничтожить вручную. Значение по умолчанию — FALSE. Это значение равно TRUE только в том случае, если все объекты анимации, принадлежащих к группе выделяются динамически с помощью оператора new.|
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Указывает, как удалить опорные кадры. Если это значение равно TRUE, все ключевые кадры удаляются и уничтожаются; в противном случае они удаляются только из списка. Значение по умолчанию — TRUE.|
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|Содержит список объектов анимации.|
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|Содержит список ключевых кадров.|
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|Указывает на раскадровку анимации. Этот указатель является допустимым только после вызова на анимировать.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|Уникальный идентификатор группы анимации.|
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|Указатель на контроллер анимации, к которой принадлежит эта группа.|

## <a name="remarks"></a>Примечания

Группы анимации автоматически создаются контроллером анимации (CAnimationController), при добавлении объектов анимации с помощью CAnimationController::AddAnimationObject. Группу анимации идентифицируется GroupID, которое обычно передано как параметр для управления группами анимации. GroupID берется из первого объекта анимации, добавляемый в новую группу анимации. Раскадровку анимации инкапсулированный создается после вызова CAnimationController::AnimateGroup и может осуществляться через m_pStoryboard открытый член.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAnimationGroup`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="_dtorcanimationgroup"></a>  CAnimationGroup:: ~ CAnimationGroup

Деструктор Вызывается при уничтожении группу анимации.

```
~CAnimationGroup();
```

##  <a name="addkeyframes"></a>  CAnimationGroup::AddKeyframes

Вспомогательный класс, раскадровки, добавляющий опорные кадры.

```
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на объект storyboard COM.

*bAddDeep*<br/>
Указывает, является ли этот метод должен добавить к раскадровки опорные кадры, которые зависят от других опорных кадрах.

##  <a name="addtransitions"></a>  CAnimationGroup::AddTransitions

Вспомогательный класс, добавляющий переходы к раскадровке.

```
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на объект storyboard COM.

*bDependOnKeyframes*

##  <a name="animate"></a>  CAnimationGroup::Animate

Анимирует группу.

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>Параметры

*pManager*<br/>
*pTimer*
*bScheduleNow*

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод создает внутренний раскадровку, создает и применяет переходы и планирует анимации, если bScheduleNow имеет значение TRUE. Если bScheduleNow имеет значение FALSE, необходимо вызвать анимации в указанное время начала расписания.

##  <a name="applytransitions"></a>  CAnimationGroup::ApplyTransitions

Применяется переходы к объектам анимации.

```
void ApplyTransitions();
```

### <a name="remarks"></a>Примечания

Этот метод УТВЕРЖДЕНИЯ в режиме отладки, если раскадровка не был создан. Он создает все переходы, во-первых, затем добавляет «static» опорных кадров (опорные кадры, которые зависят от смещения), добавляет переходов, которые не зависят от опорные кадры, добавляет опорные кадры, в зависимости от того, переходы и другие ключевые кадры и, наконец добавляет переходов, которые зависят от опорные кадры .

##  <a name="canimationgroup"></a>  CAnimationGroup::CAnimationGroup

Создает группу анимации.

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>Параметры

*pParentController*<br/>
Указатель на контроллер анимации, который создает группу.

*nGroupID*<br/>
Указывает GroupID.

##  <a name="createtransitions"></a>  CAnimationGroup::CreateTransitions

Вспомогательный метод, создающий объекты COM перехода.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Возвращаемое значение

ИСТИНА, если метод выполнен успешно, в противном случае — значение FALSE.

##  <a name="findanimationobject"></a>  CAnimationGroup::FindAnimationObject

Выполняет поиск объекта анимации, содержащую нужную переменную указанным анимации.

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Параметры

*pVariable*<br/>
Указатель на переменную анимации.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект анимации, или значение NULL, если анимация объект не найден.

##  <a name="getgroupid"></a>  CAnimationGroup::GetGroupID

Возвращает GroupID.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор группы.

##  <a name="m_bautocleartransitions"></a>  CAnimationGroup::m_bAutoclearTransitions

Указывает, как очистить переходы из анимации объектов, принадлежащих к группе. Если этот элемент имеет значение TRUE, переходы, удаляются автоматически, при анимации был запланирован. В противном случае необходимо вручную удалить переходы.

```
BOOL m_bAutoclearTransitions;
```

##  <a name="m_bautodestroyanimationobjects"></a>  CAnimationGroup::m_bAutodestroyAnimationObjects

Указывает, как для уничтожения объектов анимации. Если этот параметр имеет значение TRUE, объекты анимации будут уничтожены автоматически при удалении группы. В противном случае объекты анимации необходимо уничтожить вручную. Значение по умолчанию — FALSE. Это значение равно TRUE только в том случае, если все объекты анимации, принадлежащих к группе выделяются динамически с помощью оператора new.

```
BOOL m_bAutodestroyAnimationObjects;
```

##  <a name="m_bautodestroykeyframes"></a>  CAnimationGroup::m_bAutodestroyKeyframes

Указывает, как удалить опорные кадры. Если это значение равно TRUE, все ключевые кадры удаляются и уничтожаются; в противном случае они удаляются только из списка. Значение по умолчанию — TRUE.

```
BOOL m_bAutodestroyKeyframes;
```

##  <a name="m_lstanimationobjects"></a>  CAnimationGroup::m_lstAnimationObjects

Содержит список объектов анимации.

```
CObList m_lstAnimationObjects;
```

##  <a name="m_lstkeyframes"></a>  CAnimationGroup::m_lstKeyFrames

Содержит список ключевых кадров.

```
CObList m_lstKeyFrames;
```

##  <a name="m_ngroupid"></a>  CAnimationGroup::m_nGroupID

Уникальный идентификатор группы анимации.

```
UINT32 m_nGroupID;
```

##  <a name="m_pparentcontroller"></a>  CAnimationGroup::m_pParentController

Указатель на контроллер анимации, к которой принадлежит эта группа.

```
CAnimationController* m_pParentController;
```

##  <a name="m_pstoryboard"></a>  CAnimationGroup::m_pStoryboard

Указывает на раскадровку анимации. Этот указатель является допустимым только после вызова на анимировать.

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

##  <a name="removekeyframes"></a>  CAnimationGroup::RemoveKeyframes

Удаляет и при необходимости удаляет все опорные кадры, которые принадлежат группе анимации.

```
void RemoveKeyframes();
```

### <a name="remarks"></a>Примечания

Если член m_bAutodestroyKeyframes имеет значение TRUE, то опорные кадры удаляются и из строя, в противном случае опорные кадры, просто удаляются из во внутренний список ключевых кадров.

##  <a name="removetransitions"></a>  CAnimationGroup::RemoveTransitions

Удаляет переходы из объекта анимации, которые принадлежат группе анимации.

```
void RemoveTransitions();
```

### <a name="remarks"></a>Примечания

Если флаг m_bAutoclearTransitions имеет значение TRUE, этот метод обрабатывает в цикле всех объектов анимации, которые принадлежат к группе и вызывает CAnimationObject::ClearTransitions(FALSE).

##  <a name="schedule"></a>  CAnimationGroup::Schedule

Планирует анимации в указанное время.

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>Параметры

*pTimer*<br/>
Указатель на таймер анимации.

*time*<br/>
Указывает время для выполнения анимации.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; Значение FALSE при сбое метода, или если анимация не был вызван с bScheduleNow значение FALSE.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы запланировать анимации в указанное время. Необходимо вызвать анимировать с bScheduleNow, во-первых, равным FALSE.

##  <a name="setautodestroytransitions"></a>  CAnimationGroup::SetAutodestroyTransitions

Указывает, что переходы уничтожить всех объектов анимации, которые принадлежат группе автоматически.

```
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*bAutoDestroy*<br/>
Указывает, как для уничтожения переходов.

### <a name="remarks"></a>Примечания

Это значение равно FALSE, только в том случае, если выделить переходы в стеке. Значение по умолчанию — TRUE, поэтому настоятельно рекомендуется для выделения объектов перехода с помощью оператора new.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
