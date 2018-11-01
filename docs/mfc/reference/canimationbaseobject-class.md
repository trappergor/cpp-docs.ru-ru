---
title: Класс CAnimationBaseObject
ms.date: 11/04/2016
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
ms.openlocfilehash: 6527abf5c91cf440bbbe76d0d5fe49ce2c5dbef7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430450"
---
# <a name="canimationbaseobject-class"></a>Класс CAnimationBaseObject

Базовый класс для всех объектов анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Перегружен. Создает объект анимации.|
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#canimationbaseobject__~canimationbaseobject)|Деструктор Вызывается при уничтожении объекта анимации.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|Добавляет переходы на раскадровку с переменной инкапсулированный анимации.|
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|Удаляет все связанные с ней переходы.|
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|Определяет, содержит ли объект анимации переменной анимации.|
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|Создает переходы, связанное с объектом анимации.|
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Отсоединяет объекта анимации из родительского контроллер анимации.|
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Задает целочисленное значение изменено обработчик событий.|
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Устанавливает значение изменено обработчик событий.|
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|Сообщает, автоматическое удаление связанных перехода.|
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Возвращает идентификатор текущей группы.|
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Возвращает идентификатор текущего объекта.|
|[CAnimationBaseObject::GetUserData](#getuserdata)|Возвращает данные, определенные пользователем.|
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|Задает флаг, который упорядочивает автоматически уничтожить переходов.|
|[CAnimationBaseObject::SetID](#setid)|Задает новые идентификаторы.|
|[CAnimationBaseObject::SetUserData](#setuserdata)|Задает определяемые пользователем данные.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|Собирает указатели на переменные автономной анимации.|
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Устанавливает связь между переменными анимации, содержащиеся в объекта анимации и их контейнера.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Указывает, следует ли автоматически удалить связанные с ней переходы.|
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Содержит определяемые пользователем данные.|
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Указывает идентификатор группы объекта анимации.|
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Указывает идентификатор объекта анимации объекта.|
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Указатель на родительский контроллер анимации.|

## <a name="remarks"></a>Примечания

Этот класс реализует основные методы для всех объектов анимации. Объекта анимации можно представляют собой значения, точки, размер, прямоугольник или цвет в приложения, а также любые пользовательские сущности. Объекты анимации хранятся в группах анимации (см. в разделе CAnimationGroup). Каждая группа может быть анимировано отдельно и могут рассматриваться как аналогичен раскадровки. Объекта анимации инкапсулирует одну или несколько анимации переменных (см. в разделе CAnimationVariable), в зависимости от его логическое представление. Например CAnimationRect содержит четыре переменные анимации — одну переменную для каждой стороны прямоугольника. Каждый класс анимации объекта предоставляет перегруженный метод AddTransition, который должен использоваться для применения переходы к переменным инкапсулированный анимации. Объекта анимации, можно определить по ИД объекта (при необходимости) и по идентификатору группы. Идентификатор группы необходим для размещения объекта анимации к нужной группе, но если не указан идентификатор группы, объект помещается в группу по умолчанию с Идентификатором 0. Если вы вызываете SetID с разных GroupID, объекта анимации будут перемещены в другую группу (новая группа создается при необходимости).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="_dtorcanimationbaseobject"></a>  CAnimationBaseObject:: ~ CAnimationBaseObject

Деструктор Вызывается при уничтожении объекта анимации.

```
virtual ~CAnimationBaseObject();
```

##  <a name="applytransitions"></a>  CAnimationBaseObject::ApplyTransitions

Добавляет переходы на раскадровку с переменной инкапсулированный анимации.

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку.

*bDependOnKeyframes*<br/>
Со значением FALSE данный метод добавляет только таких переходов, которые не зависят от опорные кадры.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переходы были добавлены успешно.

### <a name="remarks"></a>Примечания

Добавляет связанные с ней переходы, которые были добавлены с AddTransition (перегруженных методов в производных классах) в раскадровку.

##  <a name="canimationbaseobject"></a>  CAnimationBaseObject::CAnimationBaseObject

Создает объект анимации.

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Указывает идентификатор группы.

*nObjectID*<br/>
Указывает идентификатор объекта.

*dwUserData*<br/>
Определяемые пользователем данные, которые можно связанный с объектом анимации и получать более поздней версии во время выполнения.

### <a name="remarks"></a>Примечания

Создает объекты анимации и присваивает идентификатор объекта по умолчанию (0) и идентификатор группы (0).

##  <a name="cleartransitions"></a>  CAnimationBaseObject::ClearTransitions

Удаляет все связанные с ней переходы.

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Параметры

*bAutodestroy*<br/>
Указывает необходимость уничтожения объектов перехода автоматически, или просто удалить их из связанного списка.

### <a name="remarks"></a>Примечания

Удаляет все связанные с ней переходы и удаляет их, если bAutodestroy или m_bAutodestroyTransitions флаг имеет значение TRUE. Должен быть автоматически уничтожена переходы, только в том случае, если они не размещаются в стеке. Если выше флаги имеют значение FALSE, переходы, просто удаляются из во внутренний список связанные с ней переходы.

##  <a name="containsvariable"></a>  CAnimationBaseObject::ContainsVariable

Определяет, содержит ли объект анимации переменной анимации.

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Параметры

*pVariable*<br/>
Указатель на переменную анимации.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если эта переменная анимации содержится в объекте анимации; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод может использоваться для определения того, содержится ли переменной анимации, определяемое pVariable внутри объекта анимации. Объекта анимации, в зависимости от его типа может содержать несколько переменных анимации. Например CAnimationColor содержит три переменных, по одной для каждого компонента цвета (красного, зеленого и синего). При изменении значения переменной анимации, API анимации Windows отправляет события ValueChanged "или" IntegerValueChanged (если он включен), а параметр этого события — это указатель на интерфейс IUIAnimationVariable переменной анимации. Этот метод позволяет получить указатель к анимации из указателя в автономной COM-объекта.

##  <a name="createtransitions"></a>  CAnimationBaseObject::CreateTransitions

Создает переходы, связанное с объектом анимации.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переходы были созданы успешно. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Список переменных анимации, инкапсулированных в объекте производного анимации в цикле и создает переходы, связанные с каждой переменной анимации.

##  <a name="detachfromcontroller"></a>  CAnimationBaseObject::DetachFromController

Отсоединяет объекта анимации из родительского контроллер анимации.

```
void DetachFromController();
```

### <a name="remarks"></a>Примечания

Этот метод используется внутренне.

##  <a name="enableintegervaluechangedevent"></a>  CAnimationBaseObject::EnableIntegerValueChangedEvent

Задает целочисленное значение изменено обработчик событий.

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
Указывает, следует ли включить или отключить событие изменения значения целого числа.

### <a name="remarks"></a>Примечания

Если целочисленное значение изменено обработчик событий включена, можно обработать это событие в методе CAnimationController::OnAnimationIntegerValueChanged, который должен быть переопределен в классе CAnimationController производным. Этот метод вызывается каждый раз при изменении целочисленное значение анимации.

##  <a name="enablevaluechangedevent"></a>  CAnimationBaseObject::EnableValueChangedEvent

Устанавливает значение изменено обработчик событий.

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
Указывает, следует ли включить или отключить событие изменения значения.

### <a name="remarks"></a>Примечания

Если значение изменено обработчик событий включена, можно обработать это событие в методе CAnimationController::OnAnimationValueChanged, который должен быть переопределен в классе CAnimationController производным. Этот метод вызывается каждый раз при изменении значения анимации.

##  <a name="getanimationvariablelist"></a>  CAnimationBaseObject::GetAnimationVariableList

Собирает указатели на переменные автономной анимации.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst) = 0;
```

### <a name="parameters"></a>Параметры

*lst*<br/>
Список, должно быть заполнено анимации переменными, содержащимися в объекте анимации.

### <a name="remarks"></a>Примечания

Это чисто виртуальный метод, который должен быть переопределен в производном классе. Объекта анимации, в зависимости от его типа, содержит одну или несколько переменных анимации. Например CAnimationPoint содержит две переменные для соответственно координаты X и Y. Базовый класс CAnimationBaseObject реализует некоторые универсальные методы, которые работают на список переменных анимации: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Эти методы вызвать GetAnimationVariableList, в которой содержатся в производном классе фактическое анимации переменными, содержащимися в объекте определенной анимации, то цикл для списка и выполнять необходимые действия. При создании объекта пользовательской анимации, вам необходимо добавить lst все переменные анимации, содержащиеся в этом объекте.

##  <a name="getautodestroytransitions"></a>  CAnimationBaseObject::GetAutodestroyTransitions

Сообщает, автоматическое удаление связанных перехода.

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если значение равно TRUE, связанные с ней переходы, удаляются автоматически. Если значение равно FALSE, переход объектов должна быть освобождена путем вызова приложения.

### <a name="remarks"></a>Примечания

По умолчанию этот флаг имеет значение TRUE. Установите этот флаг только в том случае, если выделен перехода в стеке и/или переходы, должна быть освобождена в вызывающем приложении.

##  <a name="getgroupid"></a>  CAnimationBaseObject::GetGroupID

Возвращает идентификатор текущей группы.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор текущей группы.

### <a name="remarks"></a>Примечания

Этот метод позволяет получить идентификатор группы. Если идентификатор группы не было задано явно в конструктор или с помощью SetID к 0.

##  <a name="getobjectid"></a>  CAnimationBaseObject::GetObjectID

Возвращает идентификатор текущего объекта.

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор текущего объекта.

### <a name="remarks"></a>Примечания

Этот метод позволяет получить идентификатор объекта. Если идентификатор объекта не было задано явно в конструктор или с помощью SetID к 0.

##  <a name="getuserdata"></a>  CAnimationBaseObject::GetUserData

Возвращает данные, определенные пользователем.

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение пользовательских данных.

### <a name="remarks"></a>Примечания

Этот метод используется для получения пользовательских данных во время выполнения. Возвращаемое значение будет равно 0, если он не инициализирован явным образом в конструктор или с помощью SetUserData.

##  <a name="m_bautodestroytransitions"></a>  CAnimationBaseObject::m_bAutodestroyTransitions

Указывает, следует ли автоматически удалить связанные с ней переходы.

```
BOOL m_bAutodestroyTransitions;
```

##  <a name="m_dwuserdata"></a>  CAnimationBaseObject::m_dwUserData

Содержит определяемые пользователем данные.

```
DWORD m_dwUserData;
```

##  <a name="m_ngroupid"></a>  CAnimationBaseObject::m_nGroupID

Указывает идентификатор группы объекта анимации.

```
UINT32 m_nGroupID;
```

##  <a name="m_nobjectid"></a>  CAnimationBaseObject::m_nObjectID

Указывает идентификатор объекта анимации объекта.

```
UINT32 m_nObjectID;
```

##  <a name="m_pparentcontroller"></a>  CAnimationBaseObject::m_pParentController

Указатель на родительский контроллер анимации.

```
CAnimationController* m_pParentController;
```

##  <a name="setautodestroytransitions"></a>  CAnimationBaseObject::SetAutodestroyTransitions

Задает флаг, который упорядочивает автоматически уничтожить переходов.

```
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>Параметры

*bValue*<br/>
Указывает, автоматического удаления флага.

### <a name="remarks"></a>Примечания

Установите этот флаг только в том случае, если выделен перехода объектов с помощью оператора new. Если для какой-либо причине перехода объекты выделяются в стеке, автоматического удаления флага должно быть значение FALSE. По умолчанию этот флаг имеет значение TRUE.

##  <a name="setid"></a>  CAnimationBaseObject::SetID

Задает новые идентификаторы.

```
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>Параметры

*nObjectID*<br/>
Указывает идентификатор нового объекта.

*nGroupID*<br/>
Указывает новый идентификатор группы.

### <a name="remarks"></a>Примечания

Позволяет изменить идентификатор объекта и идентификатор группы. Если идентификатор новой группы отличается от идентификатора текущего, объекта анимации перемещается в другую группу (новая группа создается, если это необходимо).

##  <a name="setparentanimationobjects"></a>  CAnimationBaseObject::SetParentAnimationObjects

Устанавливает связь между переменными анимации, содержащиеся в объекта анимации и их контейнера.

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>Примечания

Это вспомогательный объект, который может использоваться для установления связи между переменными анимации, содержащиеся в объекта анимации и их контейнера. Он обрабатывает в цикле анимации переменных и задает обратный указатель на родительский объект анимации для каждой переменной анимации. В текущей реализации, фактический отношений в CAnimationBaseObject::ApplyTransitions Поэтому обратные указатели не заданы до вызова метода CAnimationGroup::Animate. Зная связи могут оказаться полезными при обработки событий и вам необходимо получить анимированный значок родительского объекта из CAnimationVariable (используйте CAnimationVariable::GetParentAnimationObject).

##  <a name="setuserdata"></a>  CAnimationBaseObject::SetUserData

Задает определяемые пользователем данные.

```
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>Параметры

*dwUserData*<br/>
Задает пользовательские данные.

### <a name="remarks"></a>Примечания

Этот метод позволяет связывать пользовательские данные с объекта анимации. Эти данные могут быть получены позднее во время выполнения, GetUserData.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
