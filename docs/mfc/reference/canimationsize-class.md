---
title: Класс CAnimationSize
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
ms.openlocfilehash: f52016afe39da900dca4847d29beccb97d829b60
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258260"
---
# <a name="canimationsize-class"></a>Класс CAnimationSize

Реализует функции объекта размера, размеры которого могут быть анимированы.

## <a name="syntax"></a>Синтаксис

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CAnimationSize::CAnimationSize](#canimationsize)|Перегружен. Создает объект размер анимации.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CAnimationSize::AddTransition](#addtransition)|Добавляет переходы для ширины и высоты.|
|[CAnimationSize::GetCX](#getcx)|Предоставляет доступ к CAnimationVariable, представляющее ширину.|
|[CAnimationSize::GetCY](#getcy)|Предоставляет доступ к CAnimationVariable, представляющий высоту.|
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для ширины и высоты.|
|[CAnimationSize::GetValue](#getvalue)|Возвращает текущее значение.|
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированный анимации переменные в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationSize::operator CSize](#operator_csize)|Преобразует CAnimationSize CSize.|
|[CAnimationSize::operator =](#operator_eq)|Назначает szSrc CAnimationSize.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationSize::m_cxValue](#m_cxvalue)|Инкапсулированный анимации переменная, которая представляет ширину анимации.|
|[CAnimationSize::m_cyValue](#m_cyvalue)|Инкапсулированный анимации переменной, представляющей высоту анимации.|

## <a name="remarks"></a>Примечания

Класс CAnimationSize инкапсулирует два объекта CAnimationVariable и может представлять в приложениях размером. Например, этот класс можно использовать для анимации с размером любыми двумя многомерный объект на экране (как прямоугольник, управления и т.д.). Чтобы использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его к контроллеру анимации с помощью CAnimationController::AddAnimationObject и вызова AddTransition для каждого перехода для применения к ширины и высоты.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationSize::AddTransition

Добавляет переходы для ширины и высоты.

```
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>Параметры

*pCXTransition*<br/>
Указатель на переход для ширины.

*pCYTransition*<br/>
Указатель на переход для высоты.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы добавить указанный переходы во внутренний список переходов для применения к анимации переменные для ширины и высоты. Добавляя переходы, они не в силу немедленно, хранятся во внутренний список. Переходы применяются (Добавление раскадровки для определенного значения) при вызове CAnimationController::AnimateGroup. Если вам не нужно применить переход к одному из измерений, можно передать значение NULL.

##  <a name="canimationsize"></a>  CAnimationSize::CAnimationSize

Создает объект размер анимации.

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*szDefault*<br/>
Задает размер по умолчанию.

*nGroupID*<br/>
Указывает идентификатор группы.

*nObjectID*<br/>
Указывает идентификатор объекта.

*dwUserData*<br/>
Задает определяемые пользователем данные.

### <a name="remarks"></a>Примечания

Объект создается со значениями по умолчанию для ширины, высоты объекта, идентификатор и идентификатор группы, в которой будет указано значение 0. Они могут быть изменены во время выполнения, используя SetDefaultValue и SetID.

##  <a name="getanimationvariablelist"></a>  CAnimationSize::GetAnimationVariableList

Помещает инкапсулированный анимации переменные в список.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Параметры

*lst*<br/>
При возврате функции, он содержит указатели на два объекта CAnimationVariable, представляющая ширину и высоту.

##  <a name="getcx"></a>  CAnimationSize::GetCX

Предоставляет доступ к CAnimationVariable, представляющее ширину.

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющее ширину.

### <a name="remarks"></a>Примечания

Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющее ширину.

##  <a name="getcy"></a>  CAnimationSize::GetCY

Предоставляет доступ к CAnimationVariable, представляющий высоту.

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий высоту.

### <a name="remarks"></a>Примечания

Можно вызвать этот метод, чтобы получить прямой доступ к базовой CAnimationVariable, представляющий высоту.

##  <a name="getdefaultvalue"></a>  CAnimationSize::GetDefaultValue

Возвращает значения по умолчанию для ширины и высоты.

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>Возвращаемое значение

CSize объект, содержащий значения по умолчанию.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для получения значения по умолчанию, который был ранее установлен конструктор или SetDefaultValue.

##  <a name="getvalue"></a>  CAnimationSize::GetValue

Возвращает текущее значение.

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>Параметры

*szValue*<br/>
Выходные данные. Содержит текущее значение при возвращении данного метода.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущее значение было успешно извлечено; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для получения текущего значения анимации размера. Если этот метод завершается ошибкой или базовые объекты COM для ширины и размер не был инициализирован, szValue содержит значение по умолчанию, которое ранее было задано в конструкторе или SetDefaultValue.

##  <a name="m_cxvalue"></a>  CAnimationSize::m_cxValue

Инкапсулированный анимации переменная, которая представляет ширину анимации.

```
CAnimationVariable m_cxValue;
```

##  <a name="m_cyvalue"></a>  CAnimationSize::m_cyValue

Инкапсулированный анимации переменной, представляющей высоту анимации.

```
CAnimationVariable m_cyValue;
```

##  <a name="operator_csize"></a>  CAnimationSize::operator CSize

Преобразует CAnimationSize CSize.

```
operator CSize();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение анимации размера, что CSize.

### <a name="remarks"></a>Примечания

Эта функция вызывает GetValue. Если GetValue для какой-либо причине происходит сбой, возвращаемый размер будет содержать значения по умолчанию для ширины и высоты.

##  <a name="operator_eq"></a>  CAnimationSize::operator =

Назначает szSrc CAnimationSize.

```
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>Параметры

*szSrc*<br/>
Ссылается на CSize или размер.

### <a name="remarks"></a>Примечания

Назначает szSrc CAnimationSize. Мы рекомендуем сделать это до начала анимации, так как этот оператор вызывает SetDefaultValue, заново базовые объекты COM для ширины и высоты, если они были созданы. Если подписка этого объекта анимации на события (ValueChanged или IntegerValueChanged), необходимо включить эти события.

##  <a name="setdefaultvalue"></a>  CAnimationSize::SetDefaultValue

Задает значение по умолчанию.

```
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>Параметры

*szDefault*<br/>
Указывает новый размер по умолчанию.

### <a name="remarks"></a>Примечания

Эта функция используется для задания значения по умолчанию для объекта анимации. Этот метод назначает значения по умолчанию ширину и высоту размер анимации. Он также воссоздает базовых объектов COM, если они были созданы. Если подписка этого объекта анимации на события (ValueChanged или IntegerValueChanged), необходимо включить эти события.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
