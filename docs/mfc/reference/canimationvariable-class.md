---
title: Класс CAnimationVariable
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
ms.openlocfilehash: 1ad14060c7607698cd647ae34fb35b6ea3ae547c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559566"
---
# <a name="canimationvariable-class"></a>Класс CAnimationVariable

Представляет переменную анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationVariable;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Создает объект переменной анимации.|
|[CAnimationVariable:: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|Деструктор Вызывается при уничтожении объекта CAnimationVariable.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationVariable::AddTransition](#addtransition)|Добавляет переход.|
|[CAnimationVariable::ApplyTransitions](#applytransitions)|Добавляет переходы из внутреннего списка, чтобы раскадровка.|
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Очищает переходов.|
|[CAnimationVariable::Create](#create)|Создает базовой переменной COM-объекта анимации.|
|[CAnimationVariable::CreateTransitions](#createtransitions)|Создает все переходы, применяемые к этой переменной анимации.|
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Включает или отключает IntegerValueChanged события.|
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|Включает или отключает события ValueChanged.|
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Возвращает значение по умолчанию.|
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Возвращает родительский объект объекта анимации.|
|[CAnimationVariable::GetValue](#getvalue)|Перегружен. Возвращает текущее значение переменной анимации.|
|[CAnimationVariable::GetVariable](#getvariable)|Возвращает указатель на IUIAnimationVariable COM-объекта.|
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию и освобождает IUIAnimationVariable COM-объекта.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Задает связь между переменной анимации и объекта анимации.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Указывает, должен ли быть удален переход на связанные объекты.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|Указывает значение по умолчанию, которое распространяется на IUIAnimationVariable.|
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|Содержит список переходов, анимация этой переменной анимации.|
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Указатель на объект анимации, инкапсулирующий этой переменной анимации.|
|[CAnimationVariable::m_variable](#m_variable)|Содержит указатель на IUIAnimationVariable COM-объекта. Значение NULL, если COM-объект еще не создан, или не удалось создать.|

## <a name="remarks"></a>Примечания

Класс CAnimationVariable инкапсулирует IUIAnimationVariable COM-объекта. Она также содержит список переходов, применяемый к переменной анимации в раскадровке. Объекты CAnimationVariable внедряются для анимации объектов, которые могут представлять в приложение анимированное значение, точки, размер, цвет и прямоугольника.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAnimationVariable`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="_dtorcanimationvariable"></a>  CAnimationVariable:: ~ CAnimationVariable

Деструктор Вызывается при уничтожении объекта CAnimationVariable.

```
virtual ~CAnimationVariable();
```

##  <a name="addtransition"></a>  CAnimationVariable::AddTransition

Добавляет переход.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Параметры

*pTransition*<br/>
Указатель на переход для добавления.

### <a name="remarks"></a>Примечания

Этот метод вызывается, чтобы добавить переход во внутренний список переходов для применения к переменной анимации. Этот список должен быть очищен при анимации был запланирован.

##  <a name="applytransitions"></a>  CAnimationVariable::ApplyTransitions

Добавляет переходы из внутреннего списка, чтобы раскадровка.

```
void ApplyTransitions(
    CAnimationController* pController,
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на родительский контроллер анимации.

*pStoryboard*<br/>
Указатель на раскадровку.

*bDependOnKeyframes*<br/>
Значение TRUE, если этот метод должен добавить переходы, которые зависят от опорных кадров.

### <a name="remarks"></a>Примечания

Этот метод добавляет переходы из внутреннего списка, чтобы раскадровка. Он вызывается из кода верхнего уровня несколько раз для добавления переходов, которые не зависят от опорных кадров и добавьте переходов, которые зависят от опорных кадров. Базовой переменной анимации COM-объект не был создан, этот метод создает на этом этапе.

##  <a name="canimationvariable"></a>  CAnimationVariable::CAnimationVariable

Создает объект переменной анимации.

```
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```

### <a name="parameters"></a>Параметры

*dblDefaultValue*<br/>
Указывает значение по умолчанию.

### <a name="remarks"></a>Примечания

Создает объект переменной анимации и задает его значение по умолчанию. Значение по умолчанию используется в том случае, когда переменная не анимируется, или не может быть анимировано.

##  <a name="cleartransitions"></a>  CAnimationVariable::ClearTransitions

Очищает переходов.

```
void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Параметры

*bAutodestroy*<br/>
Указывает, должен ли этот метод удалить объекты перехода.

### <a name="remarks"></a>Примечания

Этот метод удаляет все переходы из внутреннего списка переходов. Если bAutodestroy имеет значение TRUE, или m_bAutodestroyTransitions имеет значение TRUE, переходы будут удалены. В противном случае вызывающий объект должен освободить объекты перехода.

##  <a name="create"></a>  CAnimationVariable::Create

Создает базовой переменной COM-объекта анимации.

```
virtual BOOL Create(IUIAnimationManager* pManager);
```

### <a name="parameters"></a>Параметры

*pManager*<br/>
Указатель на диспетчер анимации.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переменной анимации был успешно создан; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод создает базовой переменной анимации COM-объект и задает его значение по умолчанию.

##  <a name="createtransitions"></a>  CAnimationVariable::CreateTransitions

Создает все переходы, применяемые к этой переменной анимации.

```
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на [IUIAnimationTransitionLibrary интерфейс](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переходы были созданы успешно. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда следует создавать переходы, которые были добавлены к переменной внутренний список переходов.

##  <a name="enableintegervaluechangedevent"></a>  CAnimationVariable::EnableIntegerValueChangedEvent

Включает или отключает IntegerValueChanged события.

```
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
TRUE — Включение событий, FALSE — отключить событие.

### <a name="remarks"></a>Примечания

При включении события ValueChanged платформа вызывает виртуальный метод CAnimationController::OnAnimationIntegerValueChanged. Необходимо переопределить его в класс, производный от CAnimationController, чтобы обработать это событие. Этот метод вызывается каждый раз при изменении целочисленное значение переменной анимации.

##  <a name="enablevaluechangedevent"></a>  CAnimationVariable::EnableValueChangedEvent

Включает или отключает события ValueChanged.

```
void EnableValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
TRUE — Включение событий, FALSE — отключить событие.

### <a name="remarks"></a>Примечания

При включении события ValueChanged платформа вызывает виртуальный метод CAnimationController::OnAnimationValueChanged. Необходимо переопределить его в класс, производный от CAnimationController, чтобы обработать это событие. Этот метод вызывается каждый раз при изменении значения переменной анимации.

##  <a name="getdefaultvalue"></a>  CAnimationVariable::GetDefaultValue

Возвращает значение по умолчанию.

```
DOUBLE GetDefaultValue() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция используется для получения значения по умолчанию переменной анимации. Значение по умолчанию можно задать в конструкторе или методом SetDefaultValue.

##  <a name="getparentanimationobject"></a>  CAnimationVariable::GetParentAnimationObject

Возвращает родительский объект объекта анимации.

```
CAnimationBaseObject* GetParentAnimationObject();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на родительский объект анимации, если связь установлена, в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Этот метод может вызываться для получения указатель на родительский объект анимации (контейнер).

##  <a name="getvalue"></a>  CAnimationVariable::GetValue

Возвращает текущее значение переменной анимации.

```
HRESULT GetValue(DOUBLE& dblValue);
HRESULT GetValue(INT32& nValue);
```

### <a name="parameters"></a>Параметры

*dblValue*<br/>
Текущее значение переменной анимации.

*nValue*<br/>
Текущее значение переменной анимации.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если было получено значение или не был создан базовой переменной анимации. В противном случае — код ошибки HRESULT.

### <a name="remarks"></a>Примечания

Этот метод может вызываться для получения текущего значения переменной анимации. Если не будет создан объект COM, dblValue будет содержать значения по умолчанию, при возврате функции.

##  <a name="getvariable"></a>  CAnimationVariable::GetVariable

Возвращает указатель на IUIAnimationVariable COM-объекта.

```
IUIAnimationVariable* GetVariable();
```

### <a name="return-value"></a>Возвращаемое значение

Допустимый указатель на IUIAnimationVariable COM-объект или значение NULL, если переменной анимации не был создан или не может быть создан.

### <a name="remarks"></a>Примечания

Эту функцию можно используйте для доступа к основного объекта IUIAnimationVariable COM и вызывать его методы напрямую, при необходимости.

##  <a name="m_bautodestroytransitions"></a>  CAnimationVariable::m_bAutodestroyTransitions

Указывает, должен ли быть удален переход на связанные объекты.

```
BOOL m_bAutodestroyTransitions;
```

### <a name="remarks"></a>Примечания

Это значение true, чтобы Принудительное удаление объектов перехода при их удаления из внутреннего списка переходов. Если это значение равно FALSE, вызвав приложения следует удалить переходы. Список всех переходов всегда очищается после анимации был запланирован. Значение по умолчанию — FALSE.

##  <a name="m_dbldefaultvalue"></a>  CAnimationVariable::m_dblDefaultValue

Указывает значение по умолчанию, которое распространяется на IUIAnimationVariable.

```
DOUBLE m_dblDefaultValue;
```

##  <a name="m_lsttransitions"></a>  CAnimationVariable::m_lstTransitions

Содержит список переходов, анимация этой переменной анимации.

```
CObList m_lstTransitions;
```

##  <a name="m_pparentobject"></a>  CAnimationVariable::m_pParentObject

Указатель на объект анимации, инкапсулирующий этой переменной анимации.

```
CAnimationBaseObject* m_pParentObject;
```

##  <a name="m_variable"></a>  CAnimationVariable::m_variable

Содержит указатель на IUIAnimationVariable COM-объекта. Значение NULL, если COM-объект еще не создан, или не удалось создать.

```
ATL::CComPtr<IUIAnimationVariable> m_variable;
```

##  <a name="setdefaultvalue"></a>  CAnimationVariable::SetDefaultValue

Задает значение по умолчанию и освобождает IUIAnimationVariable COM-объекта.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Параметры

*dblDefaultValue*<br/>
Указывает новое значение по умолчанию.

### <a name="remarks"></a>Примечания

Этот метод позволяет восстановить значение по умолчанию. Данный метод освобождает внутренней IUIAnimationVariable COM-объекта, поэтому при переменной анимации создается заново, основного объекта COM возвращает новое значение по умолчанию. Значение по умолчанию возвращается GetValue Если COM-объект, представляющий переменную анимации не создан, или в том случае, если переменная не было анимировано.

##  <a name="setparentanimationobject"></a>  CAnimationVariable::SetParentAnimationObject

Задает связь между переменной анимации и объекта анимации.

```
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```

### <a name="parameters"></a>Параметры

*pParentObject*<br/>
Указатель на объект анимации, который содержит эту переменную.

### <a name="remarks"></a>Примечания

Этот метод вызывается внутренним образом для установления однозначное соответствие между переменной анимации и объекта анимации, который инкапсулирует его.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
