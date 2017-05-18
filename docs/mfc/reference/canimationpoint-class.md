---
title: "Класс CAnimationPoint | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationPoint class
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: a6a59ad85928c199a8dd911b915076ffbd0b0e37
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="canimationpoint-class"></a>Класс CAnimationPoint
Реализует функции точки, координаты которой могут быть анимированы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|Перегружен. Создает объект CAnimationPoint.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationPoint::AddTransition](#addtransition)|Добавляет переходы для X и Y координаты.|  
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для X и Y координаты.|  
|[CAnimationPoint::GetValue](#getvalue)|Возвращает текущее значение.|  
|[CAnimationPoint::GetX](#getx)|Предоставляет доступ к CAnimationVariable для координату X.|  
|[CAnimationPoint::GetY](#gety)|Предоставляет доступ к CAnimationVariable для оси Y.|  
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированный анимации переменные в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationPoint::operator CPoint](#operator_cpoint)|Преобразует CAnimationPoint CPoint.|  
|[CAnimationPoint::operator =](#operator_eq)|Назначает ptSrc CAnimationPoint.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationPoint::m_xValue](#m_xvalue)|Инкапсулированный анимации переменной, представляющей X координат точки анимации.|  
|[CAnimationPoint::m_yValue](#m_yvalue)|Переменная инкапсулированный анимации, представляющее координату Y точки анимации.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationPoint инкапсулирует двух объектов CAnimationVariable и может представлять в приложениях точку. Например этот класс можно использовать для анимации позицию любого объекта на экране (например, текстовая строка, круг, точки и т. д). Использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его с помощью CAnimationController::AddAnimationObject контроллер анимации и вызова AddTransition для каждого перехода для применения к координатам X и Y.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationPoint`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationPoint::AddTransition  
 Добавляет переходы для X и Y координаты.  
  
```  
void AddTransition(
    CBaseTransition* pXTransition,  
    CBaseTransition* pYTransition);
```  
  
### <a name="parameters"></a>Параметры  
 `pXTransition`  
 Указатель перемещения на X координат.  
  
 `pYTransition`  
 Координат указателя для перехода для значения Y.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для Добавление указанного переходов во внутренний список переходов для применения к анимации переменные для X и Y координаты. При добавлении переходов, они не применяются сразу и хранятся в внутренний список. Переходы применяются (Добавление в раскадровку для определенного значения) при вызове CAnimationController::AnimateGroup. Если не нужно применить переход к одному из координат, можно передать значение NULL.  
  
##  <a name="canimationpoint"></a>CAnimationPoint::CAnimationPoint  
 Создает объект CAnimationPoint.  
  
```  
CAnimationPoint();

 
CAnimationPoint(
    const CPoint& ptDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `ptDefault`  
 Задает координаты точки по умолчанию.  
  
 `nGroupID`  
 Указывает идентификатор группы.  
  
 `nObjectID`  
 Указывает идентификатор объекта.  
  
 `dwUserData`  
 Задает определяемые пользователем данные.  
  
### <a name="remarks"></a>Примечания  
 Создает объект CAnimationPoint со свойствами по умолчанию: по умолчанию координаты точки, идентификатор группы и идентификатор объекта имеют значение 0.  
  
##  <a name="getanimationvariablelist"></a>CAnimationPoint::GetAnimationVariableList  
 Помещает инкапсулированный анимации переменные в список.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Параметры  
 `lst`  
 Когда функция возвращает значение, он содержит указатели на два CAnimationVariable объекты, представляющие координаты X и Y.  
  
##  <a name="getdefaultvalue"></a>CAnimationPoint::GetDefaultValue  
 Возвращает значения по умолчанию для X и Y координаты.  
  
```  
CPoint GetDefaultValue();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Точка содержит значение по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения значения по умолчанию, которой было установлено ранее, конструктор или SetDefaultValue.  
  
##  <a name="getvalue"></a>CAnimationPoint::GetValue  
 Возвращает текущее значение.  
  
```  
BOOL GetValue(CPoint& ptValue);
```  
  
### <a name="parameters"></a>Параметры  
 `ptValue`  
 Выходные данные. Содержит текущее значение при возвращении данного метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если текущее значение были успешно извлечены; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения текущего значения анимации точки. Если этот метод завершается с ошибкой или базового COM-объектов для X и Y координаты не был инициализирован, ptValue содержит значение по умолчанию, которое ранее было задано в конструкторе или SetDefaultValue.  
  
##  <a name="getx"></a>CAnimationPoint::GetX  
 Предоставляет доступ к CAnimationVariable для координату X.  
  
```  
CAnimationVariable& GetX();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на инкапсулированный CAnimationVariable, представляющий X координации.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий X координации.  
  
##  <a name="gety"></a>CAnimationPoint::GetY  
 Предоставляет доступ к CAnimationVariable для оси Y.  
  
```  
CAnimationVariable& GetY();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющее координату по оси y.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющее координату по оси y.  
  
##  <a name="m_xvalue"></a>CAnimationPoint::m_xValue  
 Инкапсулированный анимации переменной, представляющей X координат точки анимации.  
  
```  
CAnimationVariable m_xValue;  
```  
  
##  <a name="m_yvalue"></a>CAnimationPoint::m_yValue  
 Переменная инкапсулированный анимации, представляющее координату Y точки анимации.  
  
```  
CAnimationVariable m_yValue;  
```  
  
##  <a name="operator_cpoint"></a>CAnimationPoint::operator CPoint  
 Преобразует CAnimationPoint CPoint.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение CAnimationPoint как CPoint.  
  
### <a name="remarks"></a>Примечания  
 Эта функция выполняется внутренний вызов метода GetValue. Если GetValue для какой-либо причине не удается, возвращенный точка будет содержать значения по умолчанию для X и Y координаты.  
  
##  <a name="operator_eq"></a>CAnimationPoint::operator =  
 Назначает ptSrc CAnimationPoint.  
  
```  
void operator=(const CPoint& ptSrc);
```  
  
### <a name="parameters"></a>Параметры  
 `ptSrc`  
 Относится к CPoint или ТОЧКИ.  
  
### <a name="remarks"></a>Примечания  
 Назначает ptSrc CAnimationPoint. Рекомендуется делать что до начала анимации, так как этот оператор вызывает SetDefaultValue, который повторно создает основной COM объектов для координаты X и Y, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо включить эти события.  
  
##  <a name="setdefaultvalue"></a>CAnimationPoint::SetDefaultValue  
 Задает значение по умолчанию.  
  
```  
void SetDefaultValue(const POINT& ptDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `ptDefault`  
 Задает значение точки по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для задания значения по умолчанию для объекта анимации. Это значение по умолчанию методы присваивает значения координат X и Y точки анимации. Также воссоздает базовых объектов COM, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо включить эти события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

