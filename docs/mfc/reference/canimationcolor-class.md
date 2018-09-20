---
title: Класс CAnimationColor | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 565881fdbc085e7046574d3d468073f49b24f565
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421025"
---
# <a name="canimationcolor-class"></a>Класс CAnimationColor

Реализует функции цвета, красный, зеленый и синий компоненты которого могут быть анимированы.

## <a name="syntax"></a>Синтаксис

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationColor::CAnimationColor](#canimationcolor)|Перегружен. Создает объект анимации цвета.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationColor::AddTransition](#addtransition)|Добавляет переходы для красного, зеленого и синего компонентов.|
|[CAnimationColor::GetB](#getb)|Предоставляет доступ к CAnimationVariable, представляющий синего компонента.|
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для компонентов цвета.|
|[CAnimationColor::GetG](#getg)|Предоставляет доступ к CAnimationVariable, представляющий зеленого компонента.|
|[CAnimationColor::GetR](#getr)|Предоставляет доступ к CAnimationVariable, представляющий красного компонента.|
|[CAnimationColor::GetValue](#getvalue)|Возвращает текущее значение.|
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированный анимации переменные в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationColor::operator COLORREF](#operator_colorref)||
|[CAnimationColor::operator =](#operator_eq)|Назначает цвет CAnimationColor.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationColor::m_bValue](#m_bvalue)|Инкапсулированный анимации переменной, представляющей синего компонента цвета анимации.|
|[CAnimationColor::m_gValue](#m_gvalue)|Инкапсулированный анимации переменной, представляющей зеленого компонента цвета анимации.|
|[CAnimationColor::m_rValue](#m_rvalue)|Инкапсулированный анимации переменной, представляющей красного компонента цвета анимации.|

## <a name="remarks"></a>Примечания

Класс CAnimationColor инкапсулирует три объекта CAnimationVariable и может представлять в приложениях цвет. Например, этот класс можно использовать для анимации цвета любого объекта на экране (такие как цвет текста, цвет фона, и т.д.). Чтобы использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его к контроллеру анимации с помощью CAnimationController::AddAnimationObject и вызова AddTransition для каждого перехода, применяемые к компонентам красного, зеленого и синего.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationColor::AddTransition

Добавляет переходы для красного, зеленого и синего компонентов.

```
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>Параметры

*pRTransition*<br/>
Переход для красного компонента.

*pGTransition*<br/>
Переход для зеленого компонента.

*pBTransition*<br/>
Переход для синего компонента.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для добавления указанного переходы во внутренний список переходов для применения к анимации переменные, представляющие компонентов цвета. Добавляя переходы, они не в силу немедленно, хранятся во внутренний список. Переходы применяются (Добавление раскадровки для определенного значения) при вызове CAnimationController::AnimateGroup. Если вам не нужно применить переход к одному из компонентов цвета, можно передать значение NULL.

##  <a name="canimationcolor"></a>  CAnimationColor::CAnimationColor

Создает объект CAnimationColor.

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Задает цвета по умолчанию.

*nGroupID*<br/>
Указывает идентификатор группы.

*nObjectID*<br/>
Указывает идентификатор объекта.

*dwUserData*<br/>
Задает определяемые пользователем данные.

### <a name="remarks"></a>Примечания

Объект создается со значениями по умолчанию для красный, зеленый, синий, идентификатор объекта и идентификатор группы, в которой будет указано значение 0. Они могут быть изменены во время выполнения, используя SetDefaultValue и SetID.

##  <a name="getanimationvariablelist"></a>  CAnimationColor::GetAnimationVariableList

Помещает инкапсулированный анимации переменные в список.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Параметры

*lst*<br/>
При возврате функции, здесь есть указатели на три CAnimationVariable объекты, представляющие красного, зеленого и синего компонентов.

##  <a name="getb"></a>  CAnimationColor::GetB

Предоставляет доступ к CAnimationVariable, представляющий синего компонента.

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий синего компонента.

### <a name="remarks"></a>Примечания

Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий синего компонента.

##  <a name="getdefaultvalue"></a>  CAnimationColor::GetDefaultValue

Возвращает значения по умолчанию для компонентов цвета.

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, содержащее значения по умолчанию для компонентов RGB.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для получения значения по умолчанию, который был ранее установлен конструктор или SetDefaultValue.

##  <a name="getg"></a>  CAnimationColor::GetG

Предоставляет доступ к CAnimationVariable, представляющий зеленого компонента.

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на компонент представления зеленый инкапсулированный CAnimationVariable.

### <a name="remarks"></a>Примечания

Можно вызвать этот метод, чтобы получить прямой доступ к базовый компонент зеленого CAnimationVariable для представления.

##  <a name="getr"></a>  CAnimationColor::GetR

Предоставляет доступ к CAnimationVariable, представляющий красного компонента.

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий красного компонента.

### <a name="remarks"></a>Примечания

Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий красного компонента.

##  <a name="getvalue"></a>  CAnimationColor::GetValue

Возвращает текущее значение.

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Выходные данные. Содержит текущее значение при возвращении данного метода.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущее значение было успешно извлечено; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для получения текущего значения анимации цвета. Если этот метод завершается ошибкой, или базового COM-объектов для компонентов цвета не был инициализирован, цвет содержит значение по умолчанию, которое ранее было задано в конструкторе или SetDefaultValue.

##  <a name="m_bvalue"></a>  CAnimationColor::m_bValue

Инкапсулированный анимации переменной, представляющей синего компонента цвета анимации.

```
CAnimationVariable m_bValue;
```

##  <a name="m_gvalue"></a>  CAnimationColor::m_gValue

Инкапсулированный анимации переменной, представляющей зеленого компонента цвета анимации.

```
CAnimationVariable m_gValue;
```

##  <a name="m_rvalue"></a>  CAnimationColor::m_rValue

Инкапсулированный анимации переменной, представляющей красного компонента цвета анимации.

```
CAnimationVariable m_rValue;
```

##  <a name="operator_colorref"></a>  CAnimationColor::operator COLORREF

```
operator COLORREF();
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="operator_eq"></a>  CAnimationColor::operator =

Назначает цвет CAnimationColor.

```
void operator=(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Указывает новое значение анимации цвета.

### <a name="remarks"></a>Примечания

Мы рекомендуем сделать это до начала анимации, так как этот оператор вызывает SetDefaultValue, заново базовые объекты COM для компонентов цвета, если они были созданы. Если подписка этого объекта анимации на события (ValueChanged или IntegerValueChanged), необходимо включить эти события.

##  <a name="setdefaultvalue"></a>  CAnimationColor::SetDefaultValue

Задает значение по умолчанию.

```
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Задает новые значения по умолчанию для красного, зеленого и синего компонентов.

### <a name="remarks"></a>Примечания

Эта функция используется для задания значения по умолчанию для объекта анимации. Этот метод назначает значения по умолчанию компонентов цвета анимации цвета. Он также воссоздает базовых объектов COM, если они были созданы. Если подписка этого объекта анимации на события (ValueChanged или IntegerValueChanged), необходимо включить эти события.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
