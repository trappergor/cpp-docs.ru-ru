---
title: "Класс CAnimationBaseObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b1fb434158d263b57fb34d15d976d9bae41c4df
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="canimationbaseobject-class"></a>Класс CAnimationBaseObject
Базовый класс для всех объектов анимации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## <a name="members"></a>Члены  
  
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
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Отсоединяет объект анимации из родительского контроллер анимации.|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Задает целочисленное значение изменено обработчика событий.|  
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Устанавливает значение изменено обработчика событий.|  
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|Указывает, автоматически удаляется связанный перехода.|  
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Возвращает идентификатор текущей группы.|  
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Возвращает идентификатор текущего объекта.|  
|[CAnimationBaseObject::GetUserData](#getuserdata)|Возвращает данные, определенные пользователем.|  
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|Задает флаг, который упорядочивает автоматически уничтожить переходов.|  
|[CAnimationBaseObject::SetID](#setid)|Задает новые идентификаторы.|  
|[CAnimationBaseObject::SetUserData](#setuserdata)|Задает определяемые пользователем данные.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|Собирает указателей на переменные автономной анимации.|  
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Устанавливает связь между переменными анимации, содержащиеся в объекта анимации и их контейнера.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Указывает, следует ли автоматически уничтожаться связанные с ней переходы.|  
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Содержит пользовательские данные.|  
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Указывает идентификатор группы объекта анимации.|  
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Указывает идентификатор объекта анимации объекта.|  
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Указатель на родительский контроллер анимации.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс реализует основные методы для всех объектов анимации. Объект анимации можно представляют значения, точки, размер, прямоугольник или цвет в приложения, а также любые пользовательские сущности. Анимации объекты хранятся в группах анимации (см. CAnimationGroup). Каждой группе могут быть анимированы отдельно и могут рассматриваться как аналог раскадровки. Объект анимации содержит одну или несколько анимации переменных (см. CAnimationVariable), в зависимости от его логическое представление. Например CAnimationRect содержит четыре переменных анимации - одну переменную для каждой стороны прямоугольника. Каждый класс анимации объекта предоставляет перегруженный метод AddTransition, который должен использоваться для применения переходов к переменным инкапсулированный анимации. Объект анимации, можно определить по ИД объекта (при необходимости) и по идентификатору группы. Идентификатор группы необходим для размещения объекта анимации в соответствующую группу, но если не указан идентификатор группы, объект помещается в группе по умолчанию с Идентификатором 0. При вызове SetID с разных GroupID объекта анимации будут перемещены в другую группу (новая группа создается при необходимости).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationBaseObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationbaseobject"></a>CAnimationBaseObject:: ~ CAnimationBaseObject  
 Деструктор Вызывается при уничтожении объекта анимации.  
  
```  
virtual ~CAnimationBaseObject();
```  
  
##  <a name="applytransitions"></a>CAnimationBaseObject::ApplyTransitions  
 Добавляет переходы на раскадровку с переменной инкапсулированный анимации.  
  
```  
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель на раскадровку.  
  
 `bDependOnKeyframes`  
 Со значением FALSE этот метод добавляет только переходы, которые не зависят от ключевых кадров.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переходы были успешно добавлены.  
  
### <a name="remarks"></a>Примечания  
 Добавляет связанные с ней переходы, которые были добавлены с AddTransition (перегруженные методы в производных классах) в раскадровку.  
  
##  <a name="canimationbaseobject"></a>CAnimationBaseObject::CAnimationBaseObject  
 Создает объект анимации.  
  
```  
CAnimationBaseObject();

 
CAnimationBaseObject(
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nGroupID`  
 Указывает идентификатор группы.  
  
 `nObjectID`  
 Указывает идентификатор объекта.  
  
 `dwUserData`  
 Определяемые пользователем данные, связанные с объектом анимации и извлечь позже, во время выполнения.  
  
### <a name="remarks"></a>Примечания  
 Создает объекты анимации и присваивает идентификатор объекта по умолчанию (0) и идентификатор группы (0).  
  
##  <a name="cleartransitions"></a>CAnimationBaseObject::ClearTransitions  
 Удаляет все связанные с ней переходы.  
  
```  
virtual void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>Параметры  
 `bAutodestroy`  
 Указывает, следует ли автоматически уничтожения объектов перехода или просто удалить их из связанного списка.  
  
### <a name="remarks"></a>Примечания  
 Удаляет все связанные с ней переходы и удаляет их, если флаг bAutodestroy или m_bAutodestroyTransitions имеет значение TRUE. Переходы должны автоматически уничтожаться только в том случае, если они не размещаются в стеке. Если выше флагов имеют значение FALSE, переходы просто удаляются из внутреннего списка связанные с ней переходы.  
  
##  <a name="containsvariable"></a>CAnimationBaseObject::ContainsVariable  
 Определяет, содержит ли объект анимации переменной анимации.  
  
```  
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>Параметры  
 `pVariable`  
 Указатель на переменную анимации.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переменной анимации, содержащихся в объекте анимации; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод можно использовать для определения переменной анимации, определяемое pVariable внутри объекта анимации. Объект анимации в зависимости от его типа, может содержать несколько переменных анимации. Например CAnimationColor содержит три переменных, по одной для каждого компонента цвета (красный, зеленый и синий). При изменении значения переменной анимации, API анимации Windows отправляет ValueChanged или IntegerValueChanged события (если он включен), а параметр этого события — это указатель на интерфейс IUIAnimationVariable переменной анимации. Этот метод позволяет получить указатель анимации из указателя на автономных COM-объекта.  
  
##  <a name="createtransitions"></a>CAnimationBaseObject::CreateTransitions  
 Создает переходы, связанное с объектом анимации.  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переходы не было создано успешно. в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Просматривает список переменных анимации, содержащийся в объекте производного анимации и создает переходы, связанные с каждой переменной анимации.  
  
##  <a name="detachfromcontroller"></a>CAnimationBaseObject::DetachFromController  
 Отсоединяет объект анимации из родительского контроллер анимации.  
  
```  
void DetachFromController();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется внутренним образом.  
  
##  <a name="enableintegervaluechangedevent"></a>CAnimationBaseObject::EnableIntegerValueChangedEvent  
 Задает целочисленное значение изменено обработчика событий.  
  
```  
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 `pController`  
 Указатель на родительский контроллер.  
  
 `bEnable`  
 Указывает, следует ли включить или отключить событие изменения целочисленное значение.  
  
### <a name="remarks"></a>Примечания  
 При включении целочисленное значение изменено обработчик событий можно обработать это событие в методе CAnimationController::OnAnimationIntegerValueChanged, который должен быть переопределен в класса, производного от CAnimationController. Этот метод вызывается каждый раз при изменении целочисленное значение анимации.  
  
##  <a name="enablevaluechangedevent"></a>CAnimationBaseObject::EnableValueChangedEvent  
 Устанавливает значение изменено обработчика событий.  
  
```  
virtual void EnableValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>Параметры  
 `pController`  
 Указатель на родительский контроллер.  
  
 `bEnable`  
 Указывает, следует ли включить или отключить событие изменения значения.  
  
### <a name="remarks"></a>Примечания  
 Если значение изменено обработчик событий включен, можно обработать это событие в методе CAnimationController::OnAnimationValueChanged, который должен быть переопределен в класса, производного от CAnimationController. Этот метод вызывается каждый раз при изменении значения анимации.  
  
##  <a name="getanimationvariablelist"></a>CAnimationBaseObject::GetAnimationVariableList  
 Собирает указателей на переменные автономной анимации.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst) = 0;  
```  
  
### <a name="parameters"></a>Параметры  
 `lst`  
 Список, должно быть заполнено анимации переменные, содержащиеся в объекте анимации.  
  
### <a name="remarks"></a>Примечания  
 Это чисто виртуальный метод, который должен быть переопределен в производном классе. Объект анимации в зависимости от его типа, содержит одну или несколько переменных анимации. Например CAnimationPoint содержит две переменные для координаты X и Y соответственно. Базовый класс CAnimationBaseObject реализует некоторые универсальные методы, которые работают на список переменных анимации: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Эти методы вызова GetAnimationVariableList, в которой содержатся в производном классе с переменными фактическое анимации, содержащийся в объекте анимации, то цикла по списку и выполнять необходимые действия. При создании объекта пользовательской анимации, чтобы lst необходимо добавить все переменные анимации, содержащиеся в этом объекте.  
  
##  <a name="getautodestroytransitions"></a>CAnimationBaseObject::GetAutodestroyTransitions  
 Указывает, автоматически удаляется связанный перехода.  
  
```  
BOOL GetAutodestroyTransitions() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если значение равно TRUE, связанные с ней переходы удаляется автоматически. Если значение равно FALSE, переход объектов должна быть освобождена путем вызова приложения.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот флаг имеет значение TRUE. Установите этот флаг только в том случае, если выделенный перехода в стеке или переходов, должна быть освобождена в вызывающем приложении.  
  
##  <a name="getgroupid"></a>CAnimationBaseObject::GetGroupID  
 Возвращает идентификатор текущей группы.  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор текущей группы.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы получить идентификатор группы. 0, в том случае, если идентификатор группы не задано явным образом в конструкторе или с SetID.  
  
##  <a name="getobjectid"></a>CAnimationBaseObject::GetObjectID  
 Возвращает идентификатор текущего объекта.  
  
```  
UINT32 GetObjectID() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор текущего объекта.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для получения идентификатора объекта. 0, в том случае, если идентификатор объекта не было задано явно в конструкторе или с SetID.  
  
##  <a name="getuserdata"></a>CAnimationBaseObject::GetUserData  
 Возвращает данные, определенные пользователем.  
  
```  
DWORD GetUserData() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение пользовательских данных.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для получения пользовательских данных во время выполнения. Возвращаемое значение будет равно 0, если он не инициализирован явным образом в конструкторе или с SetUserData.  
  
##  <a name="m_bautodestroytransitions"></a>CAnimationBaseObject::m_bAutodestroyTransitions  
 Указывает, следует ли автоматически уничтожаться связанные с ней переходы.  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
##  <a name="m_dwuserdata"></a>CAnimationBaseObject::m_dwUserData  
 Содержит пользовательские данные.  
  
```  
DWORD m_dwUserData;  
```  
  
##  <a name="m_ngroupid"></a>CAnimationBaseObject::m_nGroupID  
 Указывает идентификатор группы объекта анимации.  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_nobjectid"></a>CAnimationBaseObject::m_nObjectID  
 Указывает идентификатор объекта анимации объекта.  
  
```  
UINT32 m_nObjectID;  
```  
  
##  <a name="m_pparentcontroller"></a>CAnimationBaseObject::m_pParentController  
 Указатель на родительский контроллер анимации.  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="setautodestroytransitions"></a>CAnimationBaseObject::SetAutodestroyTransitions  
 Задает флаг, который упорядочивает автоматически уничтожить переходов.  
  
```  
void SetAutodestroyTransitions(BOOL bValue);
```  
  
### <a name="parameters"></a>Параметры  
 `bValue`  
 Указывает, автоматически уничтожить флаг.  
  
### <a name="remarks"></a>Примечания  
 Установите этот флаг только в том случае, если выделить перехода объектов с помощью оператора new. Если для какой-либо причине перехода объекты выделяются в стеке, destroy автоматического флага должно быть значение FALSE. По умолчанию этот флаг имеет значение TRUE.  
  
##  <a name="setid"></a>CAnimationBaseObject::SetID  
 Задает новые идентификаторы.  
  
```  
void SetID(
    UINT32 nObjectID,  
    UINT32 nGroupID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nObjectID`  
 Указывает идентификатор нового объекта.  
  
 `nGroupID`  
 Задает новый идентификатор группы.  
  
### <a name="remarks"></a>Примечания  
 Позволяет изменить идентификатор объекта и идентификатор группы. Если новый идентификатор группы отличается от идентификатора текущего, объекта анимации перемещается в другую группу (новая группа создается, если это необходимо).  
  
##  <a name="setparentanimationobjects"></a>CAnimationBaseObject::SetParentAnimationObjects  
 Устанавливает связь между переменными анимации, содержащиеся в объекта анимации и их контейнера.  
  
```  
virtual void SetParentAnimationObjects();
```  
  
### <a name="remarks"></a>Примечания  
 Это вспомогательный класс, который может использоваться для установления связи между переменными анимации, содержащиеся в объекта анимации и их контейнера. Он обрабатывает в цикле анимации переменных и задает обратный указатель для родительского объекта анимации для каждой переменной анимации. В текущей реализации, фактические связи в CAnimationBaseObject::ApplyTransitions Поэтому обратные указатели не заданы до вызова CAnimationGroup::Animate. Зная связи могут оказаться полезными при обработки событий, а также для получения анимации родительского объекта из CAnimationVariable (используйте CAnimationVariable::GetParentAnimationObject).  
  
##  <a name="setuserdata"></a>CAnimationBaseObject::SetUserData  
 Задает определяемые пользователем данные.  
  
```  
void SetUserData (DWORD dwUserData);
```  
  
### <a name="parameters"></a>Параметры  
 `dwUserData`  
 Указывает пользовательские данные.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы связать пользовательские данные с объекта анимации. Эти данные могут быть впоследствии получены во время выполнения GetUserData.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
