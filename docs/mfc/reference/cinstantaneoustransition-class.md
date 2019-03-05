---
title: Класс CInstantaneousTransition
ms.date: 11/04/2016
f1_keywords:
- CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::Create
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::m_dblFinalValue
helpviewer_keywords:
- CInstantaneousTransition [MFC], CInstantaneousTransition
- CInstantaneousTransition [MFC], Create
- CInstantaneousTransition [MFC], m_dblFinalValue
ms.assetid: c3d5121f-2c6b-4221-9e57-10e082a31120
ms.openlocfilehash: 6e28c7d51fd80771d0348ab42021d196f81d3474
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275131"
---
# <a name="cinstantaneoustransition-class"></a>Класс CInstantaneousTransition

Инкапсулирует мгновенный переход.

## <a name="syntax"></a>Синтаксис

```
class CInstantaneousTransition : public CBaseTransition;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInstantaneousTransition::CInstantaneousTransition](#cinstantaneoustransition)|Создает объект перехода и инициализирует его конечное значение.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CInstantaneousTransition::Create](#create)|Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CInstantaneousTransition::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|

## <a name="remarks"></a>Примечания

Во время мгновенный переход значение переменной анимации изменяется мгновенно текущее значение на указанной конечное значение. Длительность этого перехода всегда равна нулю. Так как автоматически удаляются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока то возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CInstantaneousTransition](../../mfc/reference/cinstantaneoustransition-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="cinstantaneoustransition"></a>  CInstantaneousTransition::CInstantaneousTransition

Создает объект перехода и инициализирует его конечное значение.

```
CInstantaneousTransition(DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Параметры

*dblFinalValue*<br/>
Значение переменной анимации в конце перехода.

##  <a name="create"></a>  CInstantaneousTransition::Create

Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на [IUIAnimationTransitionLibrary интерфейс](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.

##  <a name="m_dblfinalvalue"></a>  CInstantaneousTransition::m_dblFinalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_dblFinalValue;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
