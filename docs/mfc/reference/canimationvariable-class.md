---
title: "Класс CAnimationVariable | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationVariable
- afxanimationcontroller/CAnimationVariable
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariable class
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 42513c841f6dc891369d7d6640ced1aa37f90e8e
ms.lasthandoff: 02/24/2017

---
# <a name="canimationvariable-class"></a>Класс CAnimationVariable
Представляет переменную анимации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationVariable;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|Создает объект переменной анимации.|  
|[CAnimationVariable:: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|Деструктор Вызывается при уничтожении объекта CAnimationVariable.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](#addtransition)|Добавляет переход.|  
|[CAnimationVariable::ApplyTransitions](#applytransitions)|Добавляет переходы из внутреннего списка для раскадровки.|  
|[CAnimationVariable::ClearTransitions](#cleartransitions)|Очищает переходов.|  
|[CAnimationVariable::Create](#create)|Создает объект COM переменной базового анимации.|  
|[CAnimationVariable::CreateTransitions](#createtransitions)|Создает все переходы для применения к этой переменной анимации.|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Включает или отключает IntegerValueChanged события.|  
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|Включает или отключает событие ValueChanged.|  
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|Возвращает значение по умолчанию.|  
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|Возвращает родительский объект для анимации.|  
|[CAnimationVariable::GetValue](#getvalue)|Перегружен. Возвращает текущее значение переменной анимации.|  
|[CAnimationVariable::GetVariable](#getvariable)|Возвращает указатель IUIAnimationVariable COM-объект.|  
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию и освобождает IUIAnimationVariable COM-объект.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|Задает связь между переменной анимации и объекта анимации.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Указывает, следует ли удалять переход на связанные объекты.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|Указывает значение по умолчанию, который передается IUIAnimationVariable.|  
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|Содержит список переходов, анимация этой переменной анимации.|  
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|Указатель объекта анимации, который инкапсулирует этой переменной анимации.|  
|[CAnimationVariable::m_variable](#m_variable)|Хранит указатель IUIAnimationVariable COM-объект. Значение NULL, если COM-объект еще не создана, или не удалось создать.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationVariable инкапсулирует IUIAnimationVariable COM-объект. Она также содержит список переходов для применения к переменной анимации в раскадровке. Внедренные объекты CAnimationVariable для анимации объектов, которые могут представлять приложения анимированное значение, точки, размер, цвет и прямоугольника.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CAnimationVariable`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="a-namedtorcanimationvariablea--canimationvariablecanimationvariable"></a><a name="_dtorcanimationvariable"></a>CAnimationVariable:: ~ CAnimationVariable  
 Деструктор Вызывается при уничтожении объекта CAnimationVariable.  
  
```  
virtual ~CAnimationVariable();
```  
  
##  <a name="a-nameaddtransitiona--canimationvariableaddtransition"></a><a name="addtransition"></a>CAnimationVariable::AddTransition  
 Добавляет переход.  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>Параметры  
 `pTransition`  
 Переход, чтобы добавить указатель.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, чтобы добавить переход во внутренний список переходов для применения к переменной анимации. Этот список должен быть очищен, когда было запланировано анимации.  
  
##  <a name="a-nameapplytransitionsa--canimationvariableapplytransitions"></a><a name="applytransitions"></a>CAnimationVariable::ApplyTransitions  
 Добавляет переходы из внутреннего списка для раскадровки.  
  
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
 Значение TRUE, если этот метод следует добавить переходы, которые зависят от опорных кадров.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет переходы из внутреннего списка для раскадровки. Он вызывается из кода верхнего уровня несколько раз для добавления переходов, которые не зависят от ключевых кадров и добавьте переходы, которые зависят от опорных кадров. Базовой переменной анимации COM-объект не был создан, этот метод создает на этом этапе.  
  
##  <a name="a-namecanimationvariablea--canimationvariablecanimationvariable"></a><a name="canimationvariable"></a>CAnimationVariable::CAnimationVariable  
 Создает объект переменной анимации.  
  
```  
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```  
  
### <a name="parameters"></a>Параметры  
 `dblDefaultValue`  
 Указывает значение по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Создает объект переменной анимации и задает в качестве значения по умолчанию. Значение по умолчанию используется в том случае, когда переменная не анимируется или не может быть анимированы.  
  
##  <a name="a-namecleartransitionsa--canimationvariablecleartransitions"></a><a name="cleartransitions"></a>CAnimationVariable::ClearTransitions  
 Очищает переходов.  
  
```  
void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Параметры  
 `bAutodestroy`  
 Указывает, должен ли этот метод удалить объекты перехода.  
  
### <a name="remarks"></a>Примечания  
 Этот метод удаляет все переходы из внутреннего списка переходов. Если bAutodestroy имеет значение TRUE, или m_bAutodestroyTransitions имеет значение TRUE, переходы будут удалены. В противном случае вызывающий объект должен освободить объекты перехода.  
  
##  <a name="a-namecreatea--canimationvariablecreate"></a><a name="create"></a>CAnimationVariable::Create  
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
 Этот метод создает базовой переменной анимации COM-объект и задает в качестве значения по умолчанию.  
  
##  <a name="a-namecreatetransitionsa--canimationvariablecreatetransitions"></a><a name="createtransitions"></a>CAnimationVariable::CreateTransitions  
 Создает все переходы для применения к этой переменной анимации.  
  
```  
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Параметры  
`pLibrary`  
 Указатель на [IUIAnimationTransitionLibrary интерфейс](https://msdn.microsoft.com/library/windows/desktop/dd371897), определяющего библиотеки стандартных переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переходы были созданы успешно. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается платформой, когда следует создавать переходы, добавленные к переменной внутренний список переходов.  
  
##  <a name="a-nameenableintegervaluechangedeventa--canimationvariableenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>CAnimationVariable::EnableIntegerValueChangedEvent  
 Включает или отключает IntegerValueChanged события.  
  
```  
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 `pController`  
 Указатель на родительский контроллер.  
  
 `bEnable`  
 TRUE – включить события, FALSE — отключить события.  
  
### <a name="remarks"></a>Примечания  
 При включении события ValueChanged платформа вызывает виртуальный метод CAnimationController::OnAnimationIntegerValueChanged. Необходимо переопределить его в класс, производный от CAnimationController для обработки этого события. Этот метод вызывается каждый раз при изменении целочисленное значение переменной анимации.  
  
##  <a name="a-nameenablevaluechangedeventa--canimationvariableenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>CAnimationVariable::EnableValueChangedEvent  
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
 TRUE – включить события, FALSE — отключить события.  
  
### <a name="remarks"></a>Примечания  
 При включении события ValueChanged платформа вызывает виртуальный метод CAnimationController::OnAnimationValueChanged. Необходимо переопределить его в класс, производный от CAnimationController для обработки этого события. Этот метод вызывается каждый раз при изменении значения переменной анимации.  
  
##  <a name="a-namegetdefaultvaluea--canimationvariablegetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationVariable::GetDefaultValue  
 Возвращает значение по умолчанию.  
  
```  
DOUBLE GetDefaultValue() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для получения значения переменной анимации по умолчанию. Значение по умолчанию можно задать в конструкторе или методом SetDefaultValue.  
  
##  <a name="a-namegetparentanimationobjecta--canimationvariablegetparentanimationobject"></a><a name="getparentanimationobject"></a>CAnimationVariable::GetParentAnimationObject  
 Возвращает родительский объект для анимации.  
  
```  
CAnimationBaseObject* GetParentAnimationObject();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на родительский объект анимации, если было установлено отношение, в противном случае — значение NULL.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может вызываться, чтобы получить указатель на родительский объект анимации (контейнер).  
  
##  <a name="a-namegetvaluea--canimationvariablegetvalue"></a><a name="getvalue"></a>CAnimationVariable::GetValue  
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
 Этот метод может быть вызван для получения текущего значения переменной анимации. Если основной COM-объект не был создан, dblValue будет содержать значение по умолчанию, при возврате из функции.  
  
##  <a name="a-namegetvariablea--canimationvariablegetvariable"></a><a name="getvariable"></a>CAnimationVariable::GetVariable  
 Возвращает указатель IUIAnimationVariable COM-объект.  
  
```  
IUIAnimationVariable* GetVariable();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель IUIAnimationVariable COM-объекта, или значение NULL, если переменной анимации не был создан или не может быть создан.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию для доступа к базовой IUIAnimationVariable COM-объекта и при необходимости его методы вызываются напрямую.  
  
##  <a name="a-namembautodestroytransitionsa--canimationvariablembautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>CAnimationVariable::m_bAutodestroyTransitions  
 Указывает, следует ли удалять переход на связанные объекты.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
### <a name="remarks"></a>Примечания  
 Задайте значение true для принудительного удаления объектов перехода, когда они удаляются из внутреннего списка переходов. Если это значение равно FALSE, вызвав приложения следует удалить переходы. Список переходов всегда очищается после анимации был запланирован. Значение по умолчанию — FALSE.  
  
##  <a name="a-namemdbldefaultvaluea--canimationvariablemdbldefaultvalue"></a><a name="m_dbldefaultvalue"></a>CAnimationVariable::m_dblDefaultValue  
 Указывает значение по умолчанию, который передается IUIAnimationVariable.  
  
```  
DOUBLE m_dblDefaultValue;  
```  
  
##  <a name="a-namemlsttransitionsa--canimationvariablemlsttransitions"></a><a name="m_lsttransitions"></a>CAnimationVariable::m_lstTransitions  
 Содержит список переходов, анимация этой переменной анимации.  
  
```  
CObList m_lstTransitions;  
```  
  
##  <a name="a-namempparentobjecta--canimationvariablempparentobject"></a><a name="m_pparentobject"></a>CAnimationVariable::m_pParentObject  
 Указатель объекта анимации, который инкапсулирует этой переменной анимации.  
  
```  
CAnimationBaseObject* m_pParentObject;  
```  
  
##  <a name="a-namemvariablea--canimationvariablemvariable"></a><a name="m_variable"></a>CAnimationVariable::m_variable  
 Хранит указатель IUIAnimationVariable COM-объект. Значение NULL, если COM-объект еще не создана, или не удалось создать.  
  
```  
ATL::CComPtr<IUIAnimationVariable> m_variable;  
```  
  
##  <a name="a-namesetdefaultvaluea--canimationvariablesetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationVariable::SetDefaultValue  
 Задает значение по умолчанию и освобождает IUIAnimationVariable COM-объект.  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>Параметры  
 `dblDefaultValue`  
 Указывает новое значение по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы сбросить значение по умолчанию. Данный метод освобождает внутренних IUIAnimationVariable COM-объект, поэтому при заново переменной анимации, базового COM-объект возвращает новое значение по умолчанию. Если не создать COM-объект, представляющий переменную анимации или переменная не анимации GetValue возвращается значение по умолчанию.  
  
##  <a name="a-namesetparentanimationobjecta--canimationvariablesetparentanimationobject"></a><a name="setparentanimationobject"></a>CAnimationVariable::SetParentAnimationObject  
 Задает связь между переменной анимации и объекта анимации.  
  
```  
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pParentObject`  
 Указатель объекта анимации, который содержит эту переменную.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается внутренне для установления однозначное соответствие между переменной анимации и объекта анимации, который инкапсулирует его.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

