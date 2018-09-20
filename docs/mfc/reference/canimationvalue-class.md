---
title: Класс CAnimationValue | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
dev_langs:
- C++
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 378af608ed9f7498b00563e841521b69a10e0b05
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418285"
---
# <a name="canimationvalue-class"></a>Класс CAnimationValue

Реализует функции объекта анимации, имеющего одно значение.

## <a name="syntax"></a>Синтаксис

```
class CAnimationValue : public CAnimationBaseObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationValue::CAnimationValue](#canimationvalue)|Перегружен. Создает объект CAnimationValue.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationValue::AddTransition](#addtransition)|Добавляет переход для применения к значение.|
|[CAnimationValue::GetValue](#getvalue)|Перегружен. Извлекает текущее значение.|
|[CAnimationValue::GetVariable](#getvariable)|Предоставляет доступ к переменной инкапсулированный анимации.|
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|Задает значение по умолчанию.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Помещает переменную инкапсулированный анимации в список. (Переопределяет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationValue::operator DOUBLE](#operator_double)|Обеспечивает преобразование между CAnimationValue и DOUBLE.|
|[CAnimationValue::operator INT32](#operator_int32)|Обеспечивает преобразование между CAnimationValue и INT32.|
|[CAnimationValue::operator =](#operator_eq)|Перегружен. Присваивает значение INT32 CAnimationValue.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CAnimationValue::m_value](#m_value)|Инкапсулированный анимации переменной, представляющей значение анимации.|

## <a name="remarks"></a>Примечания

Класс CAnimationValue инкапсулирует объект CAnimationVariable и может представлять в приложениях одного анимированные значения. Например, этот класс можно использовать для анимированного прозрачность (эффект исчезания), угол (для поворота объектов), или любой другой вариант, если вам нужно создать анимацию в зависимости от одного анимированные значения. Чтобы использовать этот класс в приложении, просто создать экземпляр объекта этого класса, добавьте его к контроллеру анимации с помощью CAnimationController::AddAnimationObject и вызова AddTransition для каждого перехода, применяемый к значению.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationValue::AddTransition

Добавляет переход для применения к значение.

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Параметры

*pTransition*<br/>
Указатель на объект перехода.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы добавить переход внутренний список переходов для применения к переменной анимации. Добавляя переходы, они не в силу немедленно, хранятся во внутренний список. Переходы применяются (Добавление раскадровки для определенного значения) при вызове CAnimationController::AnimateGroup.

##  <a name="canimationvalue"></a>  CAnimationValue::CAnimationValue

Создает объект CAnimationValue.

```
CAnimationValue();


CAnimationValue(
    DOUBLE dblDefaultValue,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*dblDefaultValue*<br/>
Указывает значение по умолчанию.

*nGroupID*<br/>
Указывает идентификатор группы.

*nObjectID*<br/>
Указывает идентификатор объекта.

*dwUserData*<br/>
Задает определяемые пользователем данные.

### <a name="remarks"></a>Примечания

Создает объект CAnimationValue со свойствами по умолчанию: значение по умолчанию, идентификатор группы и идентификатор объекта имеют значение 0.

##  <a name="getanimationvariablelist"></a>  CAnimationValue::GetAnimationVariableList

Помещает переменную инкапсулированный анимации в список.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Параметры

*lst*<br/>
При возврате функции, он содержит указатель на CAnimationVariable, представляющий анимированное значение.

##  <a name="getvalue"></a>  CAnimationValue::GetValue

Извлекает текущее значение.

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>Параметры

*dblValue*<br/>
Выходные данные. При возврате функции он содержит текущее значение переменной анимации.

*nValue*<br/>
Выходные данные. При возврате функции он содержит текущее значение переменной анимации.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущее значение было извлечено успешно. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для получения текущего значения. Эта реализация вызывает инкапсулированный объект COM, и происходит сбой вызова, этот метод возвращает значение по умолчанию, который был ранее установлен в конструктор или с помощью SetDefaultValue.

##  <a name="getvariable"></a>  CAnimationValue::GetVariable

Предоставляет доступ к переменной инкапсулированный анимации.

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на переменную инкапсулированный анимации.

### <a name="remarks"></a>Примечания

Этот метод позволяет получить доступ к переменной инкапсулированный анимации. Из CAnimationVariable вы получаете доступ к основной объект IUIAnimationVariable, указатель может иметь значение NULL, если не был создан переменной анимации.

##  <a name="m_value"></a>  CAnimationValue::m_value

Инкапсулированный анимации переменной, представляющей значение анимации.

```
CAnimationVariable m_value;
```

##  <a name="operator_double"></a>  CAnimationValue::operator DOUBLE

Обеспечивает преобразование между CAnimationValue и DOUBLE.

```
operator DOUBLE();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение анимации.

### <a name="remarks"></a>Примечания

Обеспечивает преобразование между CAnimationValue и DOUBLE. Этот метод внутренне вызывает GetValue и не проверяет наличие ошибок. В случае сбоя GetValue возвращаемое значение будет содержать значение по умолчанию, заданные в конструкторе или с SetDefaultValue ранее.

##  <a name="operator_int32"></a>  CAnimationValue::operator INT32

Обеспечивает преобразование между CAnimationValue и INT32.

```
operator INT32();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение анимации как целое число.

### <a name="remarks"></a>Примечания

Обеспечивает преобразование между CAnimationValue и INT32. Этот метод внутренне вызывает GetValue и не проверяет наличие ошибок. В случае сбоя GetValue возвращаемое значение будет содержать значение по умолчанию, заданные в конструкторе или с SetDefaultValue ранее.

##  <a name="operator_eq"></a>  CAnimationValue::operator =

Присваивает значение типа DOUBLE CAnimationValue.

```
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>Параметры

*dblVal*<br/>
Задает значение, присваиваемое значение анимации.

*nval, полученное средством*<br/>
Задает значение, присваиваемое значение анимации.

### <a name="remarks"></a>Примечания

Присваивает значение типа DOUBLE CAnimationValue. Это значение как значение по умолчанию для переменной инкапсулированный анимации. Если подписка этого объекта анимации на события (ValueChanged или IntegerValueChanged), необходимо включить эти события.

##  <a name="setdefaultvalue"></a>  CAnimationValue::SetDefaultValue

Задает значение по умолчанию.

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Параметры

*dblDefaultValue*<br/>
Указывает значение по умолчанию.

### <a name="remarks"></a>Примечания

Этот метод позволяет установить значение по умолчанию. Значение по умолчанию возвращается приложению, при анимации не была запущена и/или базового COM-объект не был создан. Если базового COM-объект, инкапсулированный в CAnimationVarible уже был создан, этот метод повторно создает ее, поэтому может потребоваться повторно вызывать методы EnableValueChanged/EnableIntegerValueChanged.

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
