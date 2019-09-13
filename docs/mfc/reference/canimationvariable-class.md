---
title: Класс CAnimationVariable
ms.date: 03/27/2019
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
ms.openlocfilehash: b6767ed42d66aff467ef36bd2a7b5234ad181ced
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507543"
---
# <a name="canimationvariable-class"></a>Класс CAnimationVariable

Представляет переменную анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationVariable;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CAnimationVariable:: CAnimationVariable](#canimationvariable)|Конструирует объект переменной анимации.|
|[CAnimationVariable:: ~ CAnimationVariable](#_dtorcanimationvariable)|Деструктор Вызывается при уничтожении объекта CAnimationVariable.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CAnimationVariable:: Аддтранситион](#addtransition)|Добавляет переход.|
|[CAnimationVariable:: Апплитранситионс](#applytransitions)|Добавляет переходы из внутреннего списка в раскадровку.|
|[CAnimationVariable:: Клеартранситионс](#cleartransitions)|Очищает переходы.|
|[CAnimationVariable:: Create](#create)|Создает базовый COM-объект переменной анимации.|
|[CAnimationVariable:: Креатетранситионс](#createtransitions)|Создает все переходы, которые будут применены к этой переменной анимации.|
|[CAnimationVariable:: Енаблеинтежервалуечанжедевент](#enableintegervaluechangedevent)|Включает или отключает событие Интежервалуечанжед.|
|[CAnimationVariable:: Енаблевалуечанжедевент](#enablevaluechangedevent)|Включает или отключает событие ValueChanged.|
|[CAnimationVariable:: DefaultValue](#getdefaultvalue)|Возвращает значение по умолчанию.|
|[CAnimationVariable:: Жетпарентаниматионобжект](#getparentanimationobject)|Возвращает родительский объект анимации.|
|[CAnimationVariable:: GetValue](#getvalue)|Перегружен. Возвращает текущее значение переменной анимации.|
|[CAnimationVariable:: variable](#getvariable)|Возвращает указатель на COM-объект Иуианиматионвариабле.|
|[CAnimationVariable:: Сетдефаултвалуе](#setdefaultvalue)|Задает значение по умолчанию и освобождает COM-объект Иуианиматионвариабле.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CAnimationVariable:: Сетпарентаниматионобжект](#setparentanimationobject)|Задает связь между переменной анимации и объектом анимации.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationVariable:: m_bAutodestroyTransitions](#m_bautodestroytransitions)|Указывает, следует ли удалять связанные объекты перехода.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationVariable:: m_dblDefaultValue](#m_dbldefaultvalue)|Задает значение по умолчанию, которое распространяется на Иуианиматионвариабле.|
|[CAnimationVariable:: m_lstTransitions](#m_lsttransitions)|Содержит список переходов, которые анимированы для этой переменной анимации.|
|[CAnimationVariable:: m_pParentObject](#m_pparentobject)|Указатель на объект анимации, инкапсулирующий эту переменную анимации.|
|[CAnimationVariable:: m_variable](#m_variable)|Хранит указатель на COM-объект Иуианиматионвариабле. Значение NULL, если объект COM еще не создан, или если произошел сбой при создании.|

## <a name="remarks"></a>Примечания

Класс CAnimationVariable инкапсулирует COM-объект Иуианиматионвариабле. Он также содержит список переходов, которые будут применены к переменной анимации в раскадровке. Объекты CAnimationVariable внедряются в объекты анимации, которые могут представляться в приложении в виде анимированного значения, точки, размера, цвета и прямоугольника.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAnimationVariable`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="_dtorcanimationvariable"></a>CAnimationVariable:: ~ CAnimationVariable

Деструктор Вызывается при уничтожении объекта CAnimationVariable.

```
virtual ~CAnimationVariable();
```

##  <a name="addtransition"></a>CAnimationVariable:: Аддтранситион

Добавляет переход.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Параметры

*птранситион*<br/>
Указатель на добавляемый переход.

### <a name="remarks"></a>Примечания

Этот метод вызывается для добавления перехода во внутренний список переходов, применяемых к переменной анимации. Этот список должен быть сброшен при планировании анимации.

##  <a name="applytransitions"></a>CAnimationVariable:: Апплитранситионс

Добавляет переходы из внутреннего списка в раскадровку.

```
void ApplyTransitions(
    CAnimationController* pController,
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Параметры

*пконтроллер*<br/>
Указатель на родительский контроллер анимации.

*псторибоард*<br/>
Указатель на раскадровку.

*бдепендонкэйфрамес*<br/>
Значение TRUE, если этот метод должен добавлять переходы, зависящие от опорных кадров.

### <a name="remarks"></a>Примечания

Этот метод добавляет переходы из внутреннего списка в раскадровку. Он вызывается из кода верхнего уровня несколько раз для добавления переходов, которые не зависят от опорных кадров, и добавления переходов, зависящих от опорных кадров. Если базовый COM-объект переменной анимации не создан, этот метод создает его на этом этапе.

##  <a name="canimationvariable"></a>CAnimationVariable:: CAnimationVariable

Конструирует объект переменной анимации.

```
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```

### <a name="parameters"></a>Параметры

*дблдефаултвалуе*<br/>
Задает значение по умолчанию.

### <a name="remarks"></a>Примечания

Конструирует объект переменной анимации и устанавливает его значение по умолчанию. Значение по умолчанию используется, если переменная не анимирована или не может быть анимирована.

##  <a name="cleartransitions"></a>CAnimationVariable:: Клеартранситионс

Очищает переходы.

```
void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Параметры

*баутодестрой*<br/>
Указывает, должен ли этот метод удалять объекты перехода.

### <a name="remarks"></a>Примечания

Этот метод удаляет все переходы из внутреннего списка переходов. Если Баутодестрой имеет значение TRUE или m_bAutodestroyTransitions имеет значение TRUE, то переходы удаляются. В противном случае вызывающий объект должен освободить объекты перехода.

##  <a name="create"></a>CAnimationVariable:: Create

Создает базовый COM-объект переменной анимации.

```
virtual BOOL Create(IUIAnimationManager* pManager);
```

### <a name="parameters"></a>Параметры

*пманажер*<br/>
Указатель на диспетчер анимации.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переменная анимации успешно создана; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Этот метод создает COM-объект базовой анимации и задает его значение по умолчанию.

##  <a name="createtransitions"></a>CAnimationVariable:: Креатетранситионс

Создает все переходы, которые будут применены к этой переменной анимации.

```
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*плибрари*<br/>
Указатель на [интерфейс иуианиматионтранситионлибрари](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переходы успешно созданы; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой, когда ему требуется создать переходы, добавленные в внутренний список переходов переменной.

##  <a name="enableintegervaluechangedevent"></a>CAnimationVariable:: Енаблеинтежервалуечанжедевент

Включает или отключает событие Интежервалуечанжед.

```
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*пконтроллер*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
TRUE — включить событие, FALSE — отключить событие.

### <a name="remarks"></a>Примечания

Если событие ValueChanged включено, инфраструктура вызывает виртуальный метод Каниматионконтроллер:: Онаниматионинтежервалуечанжед. Чтобы обработать это событие, необходимо переопределить его в классе, производном от Каниматионконтроллер. Этот метод вызывается каждый раз при изменении целочисленного значения переменной анимации.

##  <a name="enablevaluechangedevent"></a>CAnimationVariable:: Енаблевалуечанжедевент

Включает или отключает событие ValueChanged.

```
void EnableValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*пконтроллер*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
TRUE — включить событие, FALSE — отключить событие.

### <a name="remarks"></a>Примечания

Если событие ValueChanged включено, инфраструктура вызывает виртуальный метод Каниматионконтроллер:: Онаниматионвалуечанжед. Чтобы обработать это событие, необходимо переопределить его в классе, производном от Каниматионконтроллер. Этот метод вызывается каждый раз при изменении значения переменной анимации.

##  <a name="getdefaultvalue"></a>CAnimationVariable:: DefaultValue

Возвращает значение по умолчанию.

```
DOUBLE GetDefaultValue() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция используется для получения значения по умолчанию для переменной анимации. Значение по умолчанию можно задать в конструкторе или с помощью метода Сетдефаултвалуе.

##  <a name="getparentanimationobject"></a>CAnimationVariable:: Жетпарентаниматионобжект

Возвращает родительский объект анимации.

```
CAnimationBaseObject* GetParentAnimationObject();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на родительский объект анимации, если связь установлена; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Этот метод можно вызвать для получения указателя на родительский объект анимации (контейнер).

##  <a name="getvalue"></a>CAnimationVariable:: GetValue

Возвращает текущее значение переменной анимации.

```
HRESULT GetValue(DOUBLE& dblValue);
HRESULT GetValue(INT32& nValue);
```

### <a name="parameters"></a>Параметры

*дблвалуе*<br/>
Текущее значение переменной анимации.

*Nзначение*<br/>
Текущее значение переменной анимации.

### <a name="return-value"></a>Возвращаемое значение

S_OK, если значение было успешно получено, или базовая переменная анимации не была создана. В противном случае — код ошибки HRESULT.

### <a name="remarks"></a>Примечания

Этот метод можно вызвать для получения текущего значения переменной анимации. Если базовый COM-объект не создан, Дблвалуе будет содержать значение по умолчанию, когда функция возвращает.

##  <a name="getvariable"></a>CAnimationVariable:: variable

Возвращает указатель на COM-объект Иуианиматионвариабле.

```
IUIAnimationVariable* GetVariable();
```

### <a name="return-value"></a>Возвращаемое значение

Допустимый указатель на Иуианиматионвариабле COM-объект или значение NULL, если переменная анимации не была создана или не может быть создана.

### <a name="remarks"></a>Примечания

Используйте эту функцию для доступа к базовому COM-объекту Иуианиматионвариабле и при необходимости вызывайте его методы напрямую.

##  <a name="m_bautodestroytransitions"></a>CAnimationVariable:: m_bAutodestroyTransitions

Указывает, следует ли удалять связанные объекты перехода.

```
BOOL m_bAutodestroyTransitions;
```

### <a name="remarks"></a>Примечания

Присвойте этому параметру значение TRUE, чтобы принудительно удалять объекты перехода при их удалении из внутреннего списка переходов. Если это значение равно FALSE, то переходы должны быть удалены путем вызова приложения. Список переходов всегда удаляется после запланированной анимации. Значение по умолчанию — FALSE.

##  <a name="m_dbldefaultvalue"></a>CAnimationVariable:: m_dblDefaultValue

Задает значение по умолчанию, которое распространяется на Иуианиматионвариабле.

```
DOUBLE m_dblDefaultValue;
```

##  <a name="m_lsttransitions"></a>CAnimationVariable:: m_lstTransitions

Содержит список переходов, которые анимированы для этой переменной анимации.

```
CObList m_lstTransitions;
```

##  <a name="m_pparentobject"></a>CAnimationVariable:: m_pParentObject

Указатель на объект анимации, инкапсулирующий эту переменную анимации.

```
CAnimationBaseObject* m_pParentObject;
```

##  <a name="m_variable"></a>CAnimationVariable:: m_variable

Хранит указатель на COM-объект Иуианиматионвариабле. Значение NULL, если объект COM еще не создан, или если произошел сбой при создании.

```
ATL::CComPtr<IUIAnimationVariable> m_variable;
```

##  <a name="setdefaultvalue"></a>CAnimationVariable:: Сетдефаултвалуе

Задает значение по умолчанию и освобождает COM-объект Иуианиматионвариабле.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Параметры

*дблдефаултвалуе*<br/>
Указывает новое значение по умолчанию.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы сбросить значение по умолчанию. Этот метод освобождает внутренний COM-объект Иуианиматионвариабле, поэтому при повторном создании переменной анимации базовый COM-объект получает новое значение по умолчанию. Значение по умолчанию возвращается функцией GetValue, если объект COM, представляющий переменную анимации, не создан, или если переменная не была анимирована.

##  <a name="setparentanimationobject"></a>CAnimationVariable:: Сетпарентаниматионобжект

Задает связь между переменной анимации и объектом анимации.

```
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```

### <a name="parameters"></a>Параметры

*ппарентобжект*<br/>
Указатель на объект анимации, который содержит эту переменную.

### <a name="remarks"></a>Примечания

Этот метод вызывается внутренним образом для установления связи "один к одному" между переменной анимации и объектом анимации, который его инкапсулирует.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
