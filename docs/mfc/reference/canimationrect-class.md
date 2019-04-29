---
title: Класс CAnimationRect
ms.date: 11/04/2016
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
ms.openlocfilehash: 84c4cf92894a9ece2021417445c9d7ab94ee6bdf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378184"
---
# <a name="canimationrect-class"></a>Класс CAnimationRect

Реализует функции прямоугольника, стороны которого могут быть анимированы.

## <a name="syntax"></a>Синтаксис

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CAnimationRect::CAnimationRect](#canimationrect)|Перегружен. Создает объект rect анимации.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CAnimationRect::AddTransition](#addtransition)|Добавляет переходов слева, сверху, справа и нижней координат.|
|[CAnimationRect::GetBottom](#getbottom)|Предоставляет доступ к CAnimationVariable, представляющий Нижняя координата.|
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для границы прямоугольника.|
|[CAnimationRect::GetLeft](#getleft)|Предоставляет доступ к CAnimationVariable, представляющий левая координата.|
|[CAnimationRect::GetRight](#getright)|Предоставляет доступ к CAnimationVariable, представляющий Правая координата.|
|[CAnimationRect::GetTop](#gettop)|Предоставляет доступ к CAnimationVariable, представляющий верхнюю координаты.|
|[CAnimationRect::GetValue](#getvalue)|Возвращает текущее значение.|
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|

### <a name="protected-methods"></a>Защищенные методы

|name|Описание|
|----------|-----------------|
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированный анимации переменные в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CAnimationRect::operator RECT](#operator_rect)|Преобразует CAnimationRect параметра RECT.|
|[CAnimationRect::operator =](#operator_eq)|Назначает rect CAnimationRect.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Указывает, является ли прямоугольник фиксированный размер.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Инкапсулированный анимации переменной, представляющей нижней границы анимации прямоугольника.|
|[CAnimationRect::m_leftValue](#m_leftvalue)|Инкапсулированный анимации переменной, представляющей слева граница анимации прямоугольника.|
|[CAnimationRect::m_rightValue](#m_rightvalue)|Инкапсулированный анимации переменной, представляющей справа граница анимации прямоугольника.|
|[CAnimationRect::m_szInitial](#m_szinitial)|Задает первоначальный размер анимации прямоугольника.|
|[CAnimationRect::m_topValue](#m_topvalue)|Инкапсулированный анимации переменной, представляющей верхней границы анимации прямоугольника.|

## <a name="remarks"></a>Примечания

Класс CAnimationRect инкапсулирует четыре объекта CAnimationVariable и может представлять в приложениях прямоугольник. Чтобы использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его к контроллеру анимации с помощью CAnimationController::AddAnimationObject и вызова AddTransition для каждого перехода для применения к левой, правой верхней и нижней частях координаты.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationRect::AddTransition

Добавляет переходов слева, сверху, справа и нижней координат.

```
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>Параметры

*pLeftTransition*<br/>
Задает переход левой стороны.

*pTopTransition*<br/>
Указывает перехода для верхней стороны.

*pRightTransition*<br/>
Указывает перехода для справа от оператора.

*pBottomTransition*<br/>
Указывает перехода для нижней стороны.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы добавить указанный переходы во внутренний список переходов для применения к анимации переменных для каждой стороны прямоугольника. Добавляя переходы, они не в силу немедленно, хранятся во внутренний список. Переходы применяются (Добавление раскадровки для определенного значения) при вызове CAnimationController::AnimateGroup. Если вам не нужно применить переход к одной из сторон прямоугольника, можно передать значение NULL.

##  <a name="canimationrect"></a>  CAnimationRect::CAnimationRect

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

*rect*<br/>
Указывает прямоугольник по умолчанию.

*nGroupID*<br/>
Указывает идентификатор группы.

*nObjectID*<br/>
Указывает идентификатор объекта.

*dwUserData*<br/>
Задает определяемые пользователем данные.

*pt*<br/>
Координата верхнего левого угла.

*sz*<br/>
Размер прямоугольника.

*nLeft*<br/>
Задает координату левой границы.

*nTop*<br/>
Задает координату верхнего привязан.

*nRight*<br/>
Задает координату правой границы.

*nBottom*<br/>
Задает координату нижней привязки.

### <a name="remarks"></a>Примечания

Объект создается со значениями по умолчанию для слева, сверху, справа и снизу, идентификатор объекта и идентификатор группы, в которой будет указано значение 0. Они могут быть изменены во время выполнения, используя SetDefaultValue и SetID.

##  <a name="getanimationvariablelist"></a>  CAnimationRect::GetAnimationVariableList

Помещает инкапсулированный анимации переменные в список.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Параметры

*lst*<br/>
При возврате функции, здесь есть указатели на четыре CAnimationVariable объекты, представляющие координаты прямоугольника.

##  <a name="getbottom"></a>  CAnimationRect::GetBottom

Предоставляет доступ к CAnimationVariable, представляющий Нижняя координата.

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий Нижняя координата.

### <a name="remarks"></a>Примечания

Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий Нижняя координата.

##  <a name="getdefaultvalue"></a>  CAnimationRect::GetDefaultValue

Возвращает значения по умолчанию для границы прямоугольника.

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>Возвращаемое значение

CRect значение, содержащее значения по умолчанию для левой, правой, верхней и нижней.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для получения значения по умолчанию, который был ранее установлен конструктор или SetDefaultValue.

##  <a name="getleft"></a>  CAnimationRect::GetLeft

Предоставляет доступ к CAnimationVariable, представляющий левая координата.

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий левая координата.

### <a name="remarks"></a>Примечания

Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющее координату левого.

##  <a name="getright"></a>  CAnimationRect::GetRight

Предоставляет доступ к CAnimationVariable, представляющий Правая координата.

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий Правая координата.

### <a name="remarks"></a>Примечания

Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий Правая координата.

##  <a name="gettop"></a>  CAnimationRect::GetTop

Предоставляет доступ к CAnimationVariable, представляющий верхнюю координаты.

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий верхнюю координаты.

### <a name="remarks"></a>Примечания

Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющее координату верхнего.

##  <a name="getvalue"></a>  CAnimationRect::GetValue

Возвращает текущее значение.

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Выходные данные. Содержит текущее значение при возвращении данного метода.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущее значение было успешно извлечено; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для получения текущего значения анимации прямоугольника. Если этот метод завершается ошибкой или базового COM-объектов для слева, сверху, справа и снизу, не инициализированы, rect содержит значение по умолчанию, которое ранее было задано в конструкторе или SetDefaultValue.

##  <a name="m_bfixedsize"></a>  CAnimationRect::m_bFixedSize

Указывает, является ли прямоугольник фиксированный размер.

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>Примечания

Если этот элемент имеет значение true, размер прямоугольника, является фиксированным и справа, и минимальные значения вычисляются заново каждый раз, когда верхнего левого угла перемещается в соответствии с фиксированного размера. Это значение равно TRUE, чтобы легко смещения прямоугольника по экрану. В этом случае переходы к координаты вправо и вниз, игнорируются. При создании объекта, или вызов SetDefaultValue размер сохраняются внутренне. По умолчанию этот элемент имеет значение FALSE.

##  <a name="m_bottomvalue"></a>  CAnimationRect::m_bottomValue

Инкапсулированный анимации переменной, представляющей нижней границы анимации прямоугольника.

```
CAnimationVariable m_bottomValue;
```

##  <a name="m_leftvalue"></a>  CAnimationRect::m_leftValue

Инкапсулированный анимации переменной, представляющей слева граница анимации прямоугольника.

```
CAnimationVariable m_leftValue;
```

##  <a name="m_rightvalue"></a>  CAnimationRect::m_rightValue

Инкапсулированный анимации переменной, представляющей справа граница анимации прямоугольника.

```
CAnimationVariable m_rightValue;
```

##  <a name="m_szinitial"></a>  CAnimationRect::m_szInitial

Задает первоначальный размер анимации прямоугольника.

```
CSize m_szInitial;
```

##  <a name="m_topvalue"></a>  CAnimationRect::m_topValue

Инкапсулированный анимации переменной, представляющей верхней границы анимации прямоугольника.

```
CAnimationVariable m_topValue;
```

##  <a name="operator_rect"></a>  CAnimationRect::operator RECT

Преобразует CAnimationRect параметра RECT.

```
operator RECT();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение анимации прямоугольник в качестве параметра RECT.

### <a name="remarks"></a>Примечания

Эта функция вызывает GetValue. Если GetValue для какой-либо причине происходит сбой, возвращенный RECT будет содержать значения по умолчанию для всех координат прямоугольника.

##  <a name="operator_eq"></a>  CAnimationRect::operator =

Назначает rect CAnimationRect.

```
void operator=(const RECT& rect);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Новое значение анимации прямоугольника.

### <a name="remarks"></a>Примечания

Мы рекомендуем сделать это до начала анимации, так как этот оператор вызывает SetDefaultValue, заново базовые объекты COM для компонентов цвета, если они были созданы. Если подписка этого объекта анимации на события (ValueChanged или IntegerValueChanged), необходимо включить эти события.

##  <a name="setdefaultvalue"></a>  CAnimationRect::SetDefaultValue

Задает значение по умолчанию.

```
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Задает новые значения по умолчанию для левую, сверху, справа и снизу.

### <a name="remarks"></a>Примечания

Эта функция используется для задания значения по умолчанию для объекта анимации. Этот метод назначает значения по умолчанию границы прямоугольника. Он также воссоздает базовых объектов COM, если они были созданы. Если подписка этого объекта анимации на события (ValueChanged или IntegerValueChanged), необходимо включить эти события.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
