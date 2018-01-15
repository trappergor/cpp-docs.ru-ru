---
title: "Класс CAnimationVariable | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a90db931ca53687c42263df6a4112eb478059227
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="canimationvariable-class"></a>Класс CAnimationVariable
Представляет переменную анимации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationVariable;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Создает объект переменной анимации.|  
|[CAnimationVariable:: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|Деструктор Вызывается при уничтожении объекта CAnimationVariable.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](#addtransition)|Добавляет переход.|  
|[CAnimationVariable::ApplyTransitions](#applytransitions)|Добавляет переходы из внутреннего списка на раскадровку.|  
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Очищает переходов.|  
|[CAnimationVariable::Create](#create)|Создает объект COM переменной базового анимации.|  
|[CAnimationVariable::CreateTransitions](#createtransitions)|Создает все переходы для применения к этой переменной анимации.|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Включает или отключает IntegerValueChanged событий.|  
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|Включает или отключает событие ValueChanged.|  
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Возвращает значение по умолчанию.|  
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Возвращает родительский объект анимации.|  
|[CAnimationVariable::GetValue](#getvalue)|Перегружен. Возвращает текущее значение переменной анимации.|  
|[CAnimationVariable::GetVariable](#getvariable)|Возвращает указатель IUIAnimationVariable COM-объект.|  
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию и освобождает IUIAnimationVariable COM-объекта.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Задает связь между переменной анимации и объекта анимации.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Указывает, следует ли удалять связанные перехода объектов.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|Указывает значение по умолчанию, которое распространяется на IUIAnimationVariable.|  
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|Содержит список переходов, которого должна начаться анимация этой переменной анимации.|  
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Указатель объекта анимации, который инкапсулирует этой переменной анимации.|  
|[CAnimationVariable::m_variable](#m_variable)|Хранит указатель IUIAnimationVariable COM-объект. Значение NULL, если COM-объект еще не создан, или не удалось создать.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationVariable инкапсулирует IUIAnimationVariable COM-объекта. Она также содержит список переходов, применяемый к переменной анимации в раскадровку. Внедренные объекты CAnimationVariable для анимации объектов, которые могут представлять значение анимированных приложения, точки, размер, цвет и прямоугольника.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CAnimationVariable`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationvariable"></a>CAnimationVariable:: ~ CAnimationVariable  
 Деструктор Вызывается при уничтожении объекта CAnimationVariable.  
  
```  
virtual ~CAnimationVariable();
```  
  
##  <a name="addtransition"></a>CAnimationVariable::AddTransition  
 Добавляет переход.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Параметры  
 `pTransition`  
 Указатель на переход для добавления.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, чтобы добавить переход во внутренний список переходов для применения к переменной анимации. Этот список должен быть снят, когда запланирован анимации.  
  
##  <a name="applytransitions"></a>CAnimationVariable::ApplyTransitions  
 Добавляет переходы из внутреннего списка на раскадровку.  
  
```  
void ApplyTransitions(
    CAnimationController* pController,  
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Параметры  
 `pController`  
 Указатель на родительский контроллер анимации.  
  
 `pStoryboard`  
 Указатель на раскадровку.  
  
 `bDependOnKeyframes`  
 Значение TRUE, если этот метод следует добавить переходы, которые зависят от ключевых кадров.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет переходы из внутреннего списка на раскадровку. Она вызывается из кода верхнего уровня несколько раз для добавления переходы, которые не зависят от ключевых кадров и добавьте переходы, которые зависят от ключевых кадров. Базовой переменной анимации COM-объект не был создан, этот метод создает на этом этапе.  
  
##  <a name="canimationvariable"></a>CAnimationVariable::CAnimationVariable  
 Создает объект переменной анимации.  
  
```  
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```  
  
### <a name="parameters"></a>Параметры  
 `dblDefaultValue`  
 Указывает значение по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Создает объект переменной анимации и задает значения по умолчанию. Значение по умолчанию используется в том случае, когда переменная анимация не видна, или не может быть анимированы.  
  
##  <a name="cleartransitions"></a>CAnimationVariable::ClearTransitions  
 Очищает переходов.  
  
```  
void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Параметры  
 `bAutodestroy`  
 Указывает, должен ли этот метод удалить объекты перехода.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет все переходы из внутреннего списка переходов. Если bAutodestroy имеет значение TRUE, или m_bAutodestroyTransitions имеет значение TRUE, переходы будут удалены. В противном случае вызывающий объект должен освободить объекты перехода.  
  
##  <a name="create"></a>CAnimationVariable::Create  
 Создает объект COM переменной базового анимации.  
  
```  
virtual BOOL Create(IUIAnimationManager* pManager);
```  
  
### <a name="parameters"></a>Параметры  
 `pManager`  
 Указатель диспетчера анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переменной анимации был успешно создан; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает базовую переменную анимации COM-объект и задает в качестве значения по умолчанию.  
  
##  <a name="createtransitions"></a>CAnimationVariable::CreateTransitions  
 Создает все переходы для применения к этой переменной анимации.  
  
```  
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Параметры  
`pLibrary`  
 Указатель на [IUIAnimationTransitionLibrary интерфейс](https://msdn.microsoft.com/library/windows/desktop/dd371897), который определяет библиотеку стандартных переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переходы не было создано успешно. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда необходимо создавать переходы, которые были добавлены к переменной внутренний список переходов.  
  
##  <a name="enableintegervaluechangedevent"></a>CAnimationVariable::EnableIntegerValueChangedEvent  
 Включает или отключает IntegerValueChanged событий.  
  
```  
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 `pController`  
 Указатель на родительский контроллер.  
  
 `bEnable`  
 TRUE - включить события, FALSE — отключить событие.  
  
### <a name="remarks"></a>Примечания  
 При включении событие ValueChanged платформа вызывает виртуальный метод CAnimationController::OnAnimationIntegerValueChanged. Необходимо переопределить в производный класс от CAnimationController для обработки этого события. Этот метод вызывается каждый раз при изменении целочисленное значение переменной анимации.  
  
##  <a name="enablevaluechangedevent"></a>CAnimationVariable::EnableValueChangedEvent  
 Включает или отключает событие ValueChanged.  
  
```  
void EnableValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 `pController`  
 Указатель на родительский контроллер.  
  
 `bEnable`  
 TRUE - включить события, FALSE — отключить событие.  
  
### <a name="remarks"></a>Примечания  
 При включении событие ValueChanged платформа вызывает виртуальный метод CAnimationController::OnAnimationValueChanged. Необходимо переопределить в производный класс от CAnimationController для обработки этого события. Этот метод вызывается каждый раз при изменении значения переменной анимации.  
  
##  <a name="getdefaultvalue"></a>CAnimationVariable::GetDefaultValue  
 Возвращает значение по умолчанию.  
  
```  
DOUBLE GetDefaultValue() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для получения значения по умолчанию переменной анимации. Значение по умолчанию можно задать в конструкторе или методом SetDefaultValue.  
  
##  <a name="getparentanimationobject"></a>CAnimationVariable::GetParentAnimationObject  
 Возвращает родительский объект анимации.  
  
```  
CAnimationBaseObject* GetParentAnimationObject();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на родительский объект анимации, если было установлено отношение, в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может вызываться, чтобы получить указатель на родительский объект анимации (контейнер).  
  
##  <a name="getvalue"></a>CAnimationVariable::GetValue  
 Возвращает текущее значение переменной анимации.  
  
```  
HRESULT GetValue(DOUBLE& dblValue);  
HRESULT GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>Параметры  
 `dblValue`  
 Текущее значение переменной анимации.  
  
 `nValue`  
 Текущее значение переменной анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если было получено значение или не был создан базовый переменной анимации. В противном случае — код ошибки HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может вызываться для извлечения текущего значения переменной анимации. Если основной COM-объект не был создан, dblValue будет содержать значение по умолчанию, если функция возвращает.  
  
##  <a name="getvariable"></a>CAnimationVariable::GetVariable  
 Возвращает указатель IUIAnimationVariable COM-объект.  
  
```  
IUIAnimationVariable* GetVariable();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель IUIAnimationVariable COM-объекта, или значение NULL, если переменной анимации не был создан, или не может быть создан.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для доступа к основного объекта IUIAnimationVariable COM и вызывать его методы напрямую, при необходимости.  
  
##  <a name="m_bautodestroytransitions"></a>CAnimationVariable::m_bAutodestroyTransitions  
 Указывает, следует ли удалять связанные перехода объектов.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
### <a name="remarks"></a>Примечания  
 Это значение true для принудительного удаления объектов перехода при они удаляются из внутреннего списка переходов. Если это значение равно FALSE, вызвав приложения следует удалить переходы. Список всех переходов всегда очищается после анимации был запланирован. Значение по умолчанию — FALSE.  
  
##  <a name="m_dbldefaultvalue"></a>CAnimationVariable::m_dblDefaultValue  
 Указывает значение по умолчанию, которое распространяется на IUIAnimationVariable.  
  
```  
DOUBLE m_dblDefaultValue;  
```  
  
##  <a name="m_lsttransitions"></a>CAnimationVariable::m_lstTransitions  
 Содержит список переходов, которого должна начаться анимация этой переменной анимации.  
  
```  
CObList m_lstTransitions;  
```  
  
##  <a name="m_pparentobject"></a>CAnimationVariable::m_pParentObject  
 Указатель объекта анимации, который инкапсулирует этой переменной анимации.  
  
```  
CAnimationBaseObject* m_pParentObject;  
```  
  
##  <a name="m_variable"></a>CAnimationVariable::m_variable  
 Хранит указатель IUIAnimationVariable COM-объект. Значение NULL, если COM-объект еще не создан, или не удалось создать.  
  
```  
ATL::CComPtr<IUIAnimationVariable> m_variable;  
```  
  
##  <a name="setdefaultvalue"></a>CAnimationVariable::SetDefaultValue  
 Задает значение по умолчанию и освобождает IUIAnimationVariable COM-объекта.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Параметры  
 `dblDefaultValue`  
 Указывает новое значение по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы сбросить значение по умолчанию. Данный метод освобождает внутренней IUIAnimationVariable COM-объекта, поэтому при повторном создании переменной анимации, базового COM-объект возвращает новое значение по умолчанию. Если COM-объект, представляющий переменную анимации не создан, или переменная не анимации GetValue возвращается значение по умолчанию.  
  
##  <a name="setparentanimationobject"></a>CAnimationVariable::SetParentAnimationObject  
 Задает связь между переменной анимации и объекта анимации.  
  
```  
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentObject`  
 Указатель объекта анимации, который содержит эту переменную.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается внутренним образом для установления однозначное соответствие между переменной анимации и объекта анимации, который инкапсулирует его.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
