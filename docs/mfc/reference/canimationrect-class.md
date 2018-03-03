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
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b38b1225dbce3f747efeaa7aa1e5384f7931efe0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="canimationrect-class"></a>Класс CAnimationRect
Реализует функции прямоугольника, стороны которого могут быть анимированы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationRect::CAnimationRect](#canimationrect)|Перегружен. Создает объект rect анимации.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationRect::AddTransition](#addtransition)|Добавляет переходов слева, сверху, справа и нижней координат.|  
|[CAnimationRect::GetBottom](#getbottom)|Предоставляет доступ к CAnimationVariable, представляющий Нижняя координата.|  
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для границы прямоугольника.|  
|[CAnimationRect::GetLeft](#getleft)|Предоставляет доступ к CAnimationVariable, представляющий левой координаты.|  
|[CAnimationRect::GetRight](#getright)|Предоставляет доступ к CAnimationVariable, представляющий Правая координата.|  
|[CAnimationRect::GetTop](#gettop)|Предоставляет доступ к CAnimationVariable, представляющий верхнюю координаты.|  
|[CAnimationRect::GetValue](#getvalue)|Возвращает текущее значение.|  
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированный анимации переменные в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationRect::operator RECT](#operator_rect)|Преобразует CAnimationRect RECT.|  
|[CAnimationRect::operator =](#operator_eq)|Назначает rect CAnimationRect.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Указывает, имеет ли прямоугольник фиксированный размер.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Инкапсулированный анимации переменной, которая представляет нижнюю границу анимации прямоугольник.|  
|[CAnimationRect::m_leftValue](#m_leftvalue)|Инкапсулированный анимации переменной, представляющей слева граница анимации прямоугольник.|  
|[CAnimationRect::m_rightValue](#m_rightvalue)|Инкапсулированный анимации переменной, представляющей справа граница анимации прямоугольник.|  
|[CAnimationRect::m_szInitial](#m_szinitial)|Задает первоначальный размер прямоугольника анимации.|  
|[CAnimationRect::m_topValue](#m_topvalue)|Инкапсулированный анимации переменной, которая представляет начало граница анимации прямоугольник.|  
  
## <a name="remarks"></a>Примечания  
 Класс CAnimationRect инкапсулирует четыре объекта CAnimationVariable и может представлять в приложениях прямоугольник. Использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его с помощью CAnimationController::AddAnimationObject контроллер анимации и вызова AddTransition для каждого перехода для применения к левой, правой верхней и нижней координат.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationRect`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationRect::AddTransition  
 Добавляет переходов слева, сверху, справа и нижней координат.  
  
```  
void AddTransition(
    CBaseTransition* pLeftTransition,  
    CBaseTransition* pTopTransition,  
    CBaseTransition* pRightTransition,  
    CBaseTransition* pBottomTransition);
```  
  
### <a name="parameters"></a>Параметры  
 `pLeftTransition`  
 Задает переход на левой стороне.  
  
 `pTopTransition`  
 Задает верхнюю сторону перехода.  
  
 `pRightTransition`  
 Задает переход с правой стороны.  
  
 `pBottomTransition`  
 Задает переход для нижнюю сторону.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для добавления указанного переходов во внутренний список переходов применяться к переменным анимации для каждой стороны прямоугольника. При добавлении переходов, они не, в силу немедленно и сохраняются во внутренний список. Переходы применяются (Добавление раскадровки для определенного значения) при вызове CAnimationController::AnimateGroup. Если не нужно применить переход к одной из сторон прямоугольника, можно передать значение NULL.  
  
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
 Координата левого верхнего угла.  
  
 `sz`  
 Размер прямоугольника.  
  
 `nLeft`  
 Задает координату левой границы.  
  
 `nTop`  
 Задает координату верхнего привязан.  
  
 `nRight`  
 Задает координату правой границы.  
  
 `nBottom`  
 Задает координату нижней привязан.  
  
### <a name="remarks"></a>Примечания  
 Объект создается со значениями по умолчанию слева, сверху, справа и снизу, идентификатор объекта и идентификатор группы, которому будет задано значение 0. Они могут быть изменены во время выполнения с помощью SetDefaultValue и SetID.  
  
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
 Эта функция вызывается для получения по умолчанию значение, которое было установлено ранее, конструктор или SetDefaultValue.  
  
##  <a name="getleft"></a>CAnimationRect::GetLeft  
 Предоставляет доступ к CAnimationVariable, представляющий левой координаты.  
  
```  
CAnimationVariable& GetLeft();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющий левой координаты.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий левой координаты.  
  
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
 Предоставляет доступ к CAnimationVariable, представляющий верхнюю координаты.  
  
```  
CAnimationVariable& GetTop();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на инкапсулированный CAnimationVariable, представляющий верхнюю координаты.  
  
### <a name="remarks"></a>Примечания  
 Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий верхнюю координаты.  
  
##  <a name="getvalue"></a>CAnimationRect::GetValue  
 Возвращает текущее значение.  
  
```  
BOOL GetValue(CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Выходные данные. При возвращении этим методом, содержит текущее значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если текущее значение было успешно извлечено; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения текущего значения анимации прямоугольник. Если этот метод завершается с ошибкой или базового COM-объектов для слева, сверху, справа и снизу не инициализированы, rect содержит значение по умолчанию, которое ранее было задано в конструкторе или SetDefaultValue.  
  
##  <a name="m_bfixedsize"></a>CAnimationRect::m_bFixedSize  
 Указывает, имеет ли прямоугольник фиксированный размер.  
  
```  
BOOL m_bFixedSize;  
```  
  
### <a name="remarks"></a>Примечания  
 Если этот элемент имеет значение true, размер прямоугольника, является фиксированным и вправо, и минимальные значения вычисляются при каждом создании верхнего левого угла перемещается в соответствии с фиксированного размера. Это значение равно TRUE, будет легко переместить прямоугольник по экрану. В этом случае переходы, которые применены к справа и снизу координаты игнорируются. После создания объекта или вызвать SetDefaultValue размер сохраняются самим приложением. По умолчанию этот элемент имеет значение FALSE.  
  
##  <a name="m_bottomvalue"></a>CAnimationRect::m_bottomValue  
 Инкапсулированный анимации переменной, которая представляет нижнюю границу анимации прямоугольник.  
  
```  
CAnimationVariable m_bottomValue;  
```  
  
##  <a name="m_leftvalue"></a>CAnimationRect::m_leftValue  
 Инкапсулированный анимации переменной, представляющей слева граница анимации прямоугольник.  
  
```  
CAnimationVariable m_leftValue;  
```  
  
##  <a name="m_rightvalue"></a>CAnimationRect::m_rightValue  
 Инкапсулированный анимации переменной, представляющей справа граница анимации прямоугольник.  
  
```  
CAnimationVariable m_rightValue;  
```  
  
##  <a name="m_szinitial"></a>CAnimationRect::m_szInitial  
 Задает первоначальный размер прямоугольника анимации.  
  
```  
CSize m_szInitial;  
```  
  
##  <a name="m_topvalue"></a>CAnimationRect::m_topValue  
 Инкапсулированный анимации переменной, которая представляет начало граница анимации прямоугольник.  
  
```  
CAnimationVariable m_topValue;  
```  
  
##  <a name="operator_rect"></a>CAnimationRect::operator RECT  
 Преобразует CAnimationRect RECT.  
  
```  
operator RECT();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение анимации прямоугольник в качестве RECT.  
  
### <a name="remarks"></a>Примечания  
 Эта функция автоматически вызывает GetValue. Если GetValue для какой-либо причине происходит сбой, возвращенный RECT будет содержать значения по умолчанию для всех координат прямоугольника.  
  
##  <a name="operator_eq"></a>CAnimationRect::operator =  
 Назначает rect CAnimationRect.  
  
```  
void operator=(const RECT& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Новое значение анимации прямоугольник.  
  
### <a name="remarks"></a>Примечания  
 Рекомендуется сделать это до начала анимации, так как этот оператор вызывает SetDefaultValue, который повторно создает базовые объекты COM для компонентов цвета, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо повторно включить эти события.  
  
##  <a name="setdefaultvalue"></a>CAnimationRect::SetDefaultValue  
 Задает значение по умолчанию.  
  
```  
void SetDefaultValue(const CRect& rect);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 Указывает новые значения по умолчанию для слева, сверху, справа и нижней.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно используйте для задания значения по умолчанию для объекта анимации. Этот метод присваивает значения по умолчанию границы прямоугольника. Также воссоздает базовые COM-объекты, если они были созданы. Если подписка данного объекта анимации для события (ValueChanged или IntegerValueChanged), необходимо повторно включить эти события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
