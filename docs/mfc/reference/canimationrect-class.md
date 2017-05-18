---
title: "Класс CAnimationRect | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect class
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: f935884301030166572e356fffe88439f843f2c7
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="canimationrect-class"></a>Класс CAnimationRect
Реализует функции прямоугольника, стороны которого могут быть анимированы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationRect::CAnimationRect](#canimationrect)|Перегружен. Создает объект rect анимации.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationRect::AddTransition](#addtransition)|Добавление переходов слева, сверху, справа и нижней координат.|  
|[CAnimationRect::GetBottom](#getbottom)|Предоставляет доступ к CAnimationVariable, представляющий Нижняя координата.|  
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для границы прямоугольника.|  
|[CAnimationRect::GetLeft](#getleft)|Предоставляет доступ к CAnimationVariable, представляющий левая координата.|  
|[CAnimationRect::GetRight](#getright)|Предоставляет доступ к CAnimationVariable, представляющий Правая координата.|  
|[CAnimationRect::GetTop](#gettop)|Предоставляет доступ к CAnimationVariable, представляющее верхнюю координаты.|  
|[CAnimationRect::GetValue](#getvalue)|Возвращает текущее значение.|  
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированный анимации переменные в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationRect::operator RECT](#operator_rect)|Преобразует CAnimationRect параметра RECT.|  
|[CAnimationRect::operator =](#operator_eq)|Назначает rect CAnimationRect.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Указывает, является ли прямоугольник фиксированный размер.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Переменной инкапсулированный анимации, представляющее нижнюю границу анимации прямоугольника.|  
|[CAnimationRect::m_leftValue](#m_leftvalue)|Инкапсулированный анимации переменной, представляющей слева границу анимации прямоугольника.|  
|[CAnimationRect::m_rightValue](#m_rightvalue)|Инкапсулированный анимации переменной, представляющей справа границу анимации прямоугольника.|  
|[CAnimationRect::m_szInitial](#m_szinitial)|Задает начальный размер анимации прямоугольника.|  
|[CAnimationRect::m_topValue](#m_topvalue)|Инкапсулированный анимации переменной, представляющей верхней границу анимации прямоугольника.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationRect инкапсулирует четыре объекта CAnimationVariable и может представлять в приложениях прямоугольник. Чтобы использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его с помощью CAnimationController::AddAnimationObject контроллер анимации и вызова AddTransition для каждого перехода для применения к левой, правой верхней и нижней координат.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationRect`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationRect::AddTransition  
 Добавление переходов слева, сверху, справа и нижней координат.  
  
```  
void AddTransition(
    CBaseTransition* pLeftTransition,  
    CBaseTransition* pTopTransition,  
    CBaseTransition* pRightTransition,  
    CBaseTransition* pBottomTransition);
```  
  
### <a name="parameters"></a>Параметры  
 `pLeftTransition`  
 Задает переход с левой стороны.  
  
 `pTopTransition`  
 Задает верхнюю сторону перехода.  
  
 `pRightTransition`  
 Задает переход на правой стороне.  
  
 `pBottomTransition`  
 Задает переход в нижней части.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для добавления указанного переходов во внутренний список переходов для применения анимации переменных для каждой стороны прямоугольника. При добавлении переходов, они не применяются сразу и хранятся в внутренний список. Переходы применяются (Добавление в раскадровку для определенного значения) при вызове CAnimationController::AnimateGroup. Если не требуется применить переход к одной из сторон прямоугольника, можно передать значение NULL.  
  
##  <a name="canimationrect"></a>CAnimationRect::CAnimationRect  
 Создает объект CAnimationRect.  
  
```  
CAnimationRect();

 
CAnimationRect(
    const CRect& rect,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    const CPoint& pt,  
    const CSize& sz,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    int nLeft,  
    int nTop,  
    int nRight,  
    int nBottom,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Указывает прямоугольник по умолчанию.  
  
 `nGroupID`  
 Указывает идентификатор группы.  
  
 `nObjectID`  
 Указывает идентификатор объекта.  
  
 `dwUserData`  
 Задает определяемые пользователем данные.  
  
 `pt`  
 Координаты верхнего левого угла.  
  
 `sz`  
 Размер прямоугольника.  
  
 `nLeft`  
 Задает координату левой границы.  
  
 `nTop`  
 Задает координату верхней привязан.  
  
 `nRight`  
 Задает координату правой границы.  
  
 `nBottom`  
 Задает координату нижней привязан.  
  
### <a name="remarks"></a>Примечания  
 Объект создан со значениями по умолчанию слева, сверху, справа и снизу, идентификатор объекта и идентификатор группы, которая будет иметь значение 0. Они могут быть изменены во время выполнения с помощью SetDefaultValue и SetID.  
  
##  <a name="getanimationvariablelist"></a>CAnimationRect::GetAnimationVariableList  
 Помещает инкапсулированный анимации переменные в список.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Параметры  
 `lst`  
 Когда функция возвращает значение, он содержит указатели на четыре CAnimationVariable объекты, представляющие координаты прямоугольника.  
  
##  <a name="getbottom"></a>CAnimationRect::GetBottom  
 Предоставляет доступ к CAnimationVariable, представляющий Нижняя координата.  
  
```  
CAnimationVariable& GetBottom();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющий Нижняя координата.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий Нижняя координата.  
  
##  <a name="getdefaultvalue"></a>CAnimationRect::GetDefaultValue  
 Возвращает значения по умолчанию для границы прямоугольника.  
  
```  
CRect GetDefaultValue();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 CRect значение, содержащее значения по умолчанию для левой, правой, верхней и нижней.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения значения по умолчанию, которой было установлено ранее, конструктор или SetDefaultValue.  
  
##  <a name="getleft"></a>CAnimationRect::GetLeft  
 Предоставляет доступ к CAnimationVariable, представляющий левая координата.  
  
```  
CAnimationVariable& GetLeft();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющий левая координата.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий левая координата.  
  
##  <a name="getright"></a>CAnimationRect::GetRight  
 Предоставляет доступ к CAnimationVariable, представляющий Правая координата.  
  
```  
CAnimationVariable& GetRight();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющий Правая координата.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий Правая координата.  
  
##  <a name="gettop"></a>CAnimationRect::GetTop  
 Предоставляет доступ к CAnimationVariable, представляющее верхнюю координаты.  
  
```  
CAnimationVariable& GetTop();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющее верхнюю координаты.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющее верхнюю координаты.  
  
##  <a name="getvalue"></a>CAnimationRect::GetValue  
 Возвращает текущее значение.  
  
```  
BOOL GetValue(CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Выходные данные. Содержит текущее значение при возвращении данного метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если текущее значение были успешно извлечены; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения текущего значения анимации прямоугольника. Если этот метод завершается с ошибкой или базового COM-объектов для слева, сверху, справа и снизу не будут инициализированы, rect содержит значение по умолчанию, которое ранее было задано в конструкторе или SetDefaultValue.  
  
##  <a name="m_bfixedsize"></a>CAnimationRect::m_bFixedSize  
 Указывает, является ли прямоугольник фиксированный размер.  
  
```  
BOOL m_bFixedSize;  
```  
  
### <a name="remarks"></a>Примечания  
 Если этот элемент имеет значение true, размер прямоугольника, является фиксированным и вправо, и минимальные значения вычисляются каждый раз, когда верхний левый угол перемещается в соответствии с фиксированного размера. Это значение равно TRUE, чтобы легко переместить прямоугольник по экрану. В этом случае переходы, которые применены к координатам вправо и вниз учитываются. Размер внутреннего хранения после создания объекта или вызвать SetDefaultValue. По умолчанию этот член имеет значение FALSE.  
  
##  <a name="m_bottomvalue"></a>CAnimationRect::m_bottomValue  
 Переменной инкапсулированный анимации, представляющее нижнюю границу анимации прямоугольника.  
  
```  
CAnimationVariable m_bottomValue;  
```  
  
##  <a name="m_leftvalue"></a>CAnimationRect::m_leftValue  
 Инкапсулированный анимации переменной, представляющей слева границу анимации прямоугольника.  
  
```  
CAnimationVariable m_leftValue;  
```  
  
##  <a name="m_rightvalue"></a>CAnimationRect::m_rightValue  
 Инкапсулированный анимации переменной, представляющей справа границу анимации прямоугольника.  
  
```  
CAnimationVariable m_rightValue;  
```  
  
##  <a name="m_szinitial"></a>CAnimationRect::m_szInitial  
 Задает начальный размер анимации прямоугольника.  
  
```  
CSize m_szInitial;  
```  
  
##  <a name="m_topvalue"></a>CAnimationRect::m_topValue  
 Инкапсулированный анимации переменной, представляющей верхней границу анимации прямоугольника.  
  
```  
CAnimationVariable m_topValue;  
```  
  
##  <a name="operator_rect"></a>CAnimationRect::operator RECT  
 Преобразует CAnimationRect параметра RECT.  
  
```  
operator RECT();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение анимации прямоугольник в качестве параметра RECT.  
  
### <a name="remarks"></a>Примечания  
 Эта функция выполняется внутренний вызов метода GetValue. Если GetValue для какой-либо причине не удается, возвращенный RECT будет содержать значения по умолчанию для всех координат прямоугольника.  
  
##  <a name="operator_eq"></a>CAnimationRect::operator =  
 Назначает rect CAnimationRect.  
  
```  
void operator=(const RECT& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Новое значение анимации прямоугольника.  
  
### <a name="remarks"></a>Примечания  
 Рекомендуется сделать это до начала анимации, так как этот оператор вызывает SetDefaultValue, который воссоздает базовых объектов COM для компонентов цвета, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо включить эти события.  
  
##  <a name="setdefaultvalue"></a>CAnimationRect::SetDefaultValue  
 Задает значение по умолчанию.  
  
```  
void SetDefaultValue(const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Указывает новые значения по умолчанию для left, top, вправо и вниз.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для задания значения по умолчанию для объекта анимации. Этот метод присваивает значения по умолчанию границы прямоугольника. Также воссоздает базовых объектов COM, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо включить эти события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

