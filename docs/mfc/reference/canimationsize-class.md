---
title: "Класс CAnimationSize | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationSize class
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 84b9ae3b81f72f6c0ae8e88f78357c29e8d82ffd
ms.lasthandoff: 02/24/2017

---
# <a name="canimationsize-class"></a>Класс CAnimationSize
Реализует функции объекта размера, размеры которого могут быть анимированы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationSize::CAnimationSize](#canimationsize)|Перегружен. Создает объект размера анимации.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationSize::AddTransition](#addtransition)|Добавление переходов для ширины и высоты.|  
|[CAnimationSize::GetCX](#getcx)|Предоставляет доступ к CAnimationVariable, представляющее ширину.|  
|[CAnimationSize::GetCY](#getcy)|Предоставляет доступ к CAnimationVariable, представляющее высоту.|  
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для ширины и высоты.|  
|[CAnimationSize::GetValue](#getvalue)|Возвращает текущее значение.|  
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированный анимации переменные в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationSize::operator CSize](#operator_csize)|Преобразует CAnimationSize CSize.|  
|[CAnimationSize::operator =](#operator_eq)|Назначает szSrc CAnimationSize.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationSize::m_cxValue](#m_cxvalue)|Инкапсулированный анимации переменная, которая представляет ширину анимации.|  
|[CAnimationSize::m_cyValue](#m_cyvalue)|Переменная инкапсулированный анимации, представляющий высоту анимации.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationSize инкапсулирует двух объектов CAnimationVariable и может представлять в приложениях размер. Например, этот класс можно использовать для анимации размер двух многомерных объектов на экране (например прямоугольник, управления и т. д). Использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его с помощью CAnimationController::AddAnimationObject контроллер анимации и вызова AddTransition для каждого перехода, применяемый для ширины и высоты.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationSize` 
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationSize::AddTransition  
 Добавление переходов для ширины и высоты.  
  
```  
void AddTransition(
    CBaseTransition* pCXTransition,  
    CBaseTransition* pCYTransition);
```  
  
### <a name="parameters"></a>Параметры  
 `pCXTransition`  
 Указатель на переход для ширины.  
  
 `pCYTransition`  
 Указатель на переход для высоты.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для добавления указанного переходов во внутренний список переходов для применения к переменным анимации ширины и высоты. При добавлении переходов, они не применяются сразу и хранятся в внутренний список. Переходы применяются (Добавление в раскадровку для определенного значения) при вызове CAnimationController::AnimateGroup. Если не нужно применить переход к одному из измерений, можно передать значение NULL.  
  
##  <a name="canimationsize"></a>CAnimationSize::CAnimationSize  
 Создает объект размера анимации.  
  
```  
CAnimationSize();

 
CAnimationSize(
    const CSize& szDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `szDefault`  
 Задает размер по умолчанию.  
  
 `nGroupID`  
 Указывает идентификатор группы.  
  
 `nObjectID`  
 Указывает идентификатор объекта.  
  
 `dwUserData`  
 Задает определяемые пользователем данные.  
  
### <a name="remarks"></a>Примечания  
 Объект создан со значениями по умолчанию для ширины, высоты объекта, идентификатор и идентификатор группы, которая будет иметь значение 0. Они могут быть изменены во время выполнения с помощью SetDefaultValue и SetID.  
  
##  <a name="getanimationvariablelist"></a>CAnimationSize::GetAnimationVariableList  
 Помещает инкапсулированный анимации переменные в список.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Параметры  
 `lst`  
 Когда функция возвращает значение, он содержит указатели на два объекта CAnimationVariable, представляющая ширину и высоту.  
  
##  <a name="getcx"></a>CAnimationSize::GetCX  
 Предоставляет доступ к CAnimationVariable, представляющее ширину.  
  
```  
CAnimationVariable& GetCX();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющее ширину.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющее ширину.  
  
##  <a name="getcy"></a>CAnimationSize::GetCY  
 Предоставляет доступ к CAnimationVariable, представляющее высоту.  
  
```  
CAnimationVariable& GetCY();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющее высоту.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющее высоту.  
  
##  <a name="getdefaultvalue"></a>CAnimationSize::GetDefaultValue  
 Возвращает значения по умолчанию для ширины и высоты.  
  
```  
CSize GetDefaultValue();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект CSize, содержащий значения по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения значения по умолчанию, которой было установлено ранее, конструктор или SetDefaultValue.  
  
##  <a name="getvalue"></a>CAnimationSize::GetValue  
 Возвращает текущее значение.  
  
```  
BOOL GetValue(CSize& szValue);
```  
  
### <a name="parameters"></a>Параметры  
 `szValue`  
 Выходные данные. Содержит текущее значение при возвращении данного метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если текущее значение были успешно извлечены; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения текущего значения размера анимации. Если этот метод не или базовых объектов COM, ширину и размер не был инициализирован, szValue содержит значение по умолчанию, которое ранее было задано в конструкторе или SetDefaultValue.  
  
##  <a name="m_cxvalue"></a>CAnimationSize::m_cxValue  
 Инкапсулированный анимации переменная, которая представляет ширину анимации.  
  
```  
CAnimationVariable m_cxValue;  
```  
  
##  <a name="m_cyvalue"></a>CAnimationSize::m_cyValue  
 Переменная инкапсулированный анимации, представляющий высоту анимации.  
  
```  
CAnimationVariable m_cyValue;  
```  
  
##  <a name="operator_csize"></a>CAnimationSize::operator CSize  
 Преобразует CAnimationSize CSize.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение размера анимации, CSize.  
  
### <a name="remarks"></a>Примечания  
 Эта функция выполняется внутренний вызов метода GetValue. Если GetValue для какой-либо причине не удается, возвращенный размер будет содержать значения по умолчанию для ширины и высоты.  
  
##  <a name="operator_eq"></a>CAnimationSize::operator =  
 Назначает szSrc CAnimationSize.  
  
```  
void operator=(const CSize& szSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `szSrc`  
 Относится к CSize или размер.  
  
### <a name="remarks"></a>Примечания  
 Назначает szSrc CAnimationSize. Рекомендуется сделать это до начала анимации, так как этот оператор вызывает SetDefaultValue, который воссоздает базовые объекты COM для ширины и высоты, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо включить эти события.  
  
##  <a name="setdefaultvalue"></a>CAnimationSize::SetDefaultValue  
 Задает значение по умолчанию.  
  
```  
void SetDefaultValue(const CSize& szDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `szDefault`  
 Указывает новый размер по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для задания значения по умолчанию для объекта анимации. Этот метод присваивает значения по умолчанию ширину и высоту анимации. Также воссоздает базовых объектов COM, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо включить эти события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

