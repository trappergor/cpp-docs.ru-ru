---
title: Класс CParabolicTransitionFromAcceleration
ms.date: 11/04/2016
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
ms.openlocfilehash: 3d4a073a0fd74f7564d9183779acfd66b41a9540
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274418"
---
# <a name="cparabolictransitionfromacceleration-class"></a>Класс CParabolicTransitionFromAcceleration

Инкапсулирует переход с параболическим ускорением.

## <a name="syntax"></a>Синтаксис

```
class CParabolicTransitionFromAcceleration : public CBaseTransition;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|Создает переход с параболическим ускорением и инициализирует его с указанными параметрами.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::Create](#create)|Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::m_dblAcceleration](#m_dblacceleration)|Ускорение анимации переменной во время перехода.|
|[CParabolicTransitionFromAcceleration::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|
|[CParabolicTransitionFromAcceleration::m_dblFinalVelocity](#m_dblfinalvelocity)|Скорость анимации переменной в конце перехода.|

## <a name="remarks"></a>Примечания

Во время перехода параболическим ускорением значение переменной анимации изменяется от начального значения на окончательное значение заканчивается на указанной скорости. Вы можете контролировать, насколько быстро переменная достигает конечное значение, указав интенсивность ускорение. Так как автоматически удаляются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока то возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="cparabolictransitionfromacceleration"></a>  CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration

Создает переход с параболическим ускорением и инициализирует его с указанными параметрами.

```
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,
    DOUBLE dblFinalVelocity,
    DOUBLE dblAcceleration);
```

### <a name="parameters"></a>Параметры

*dblFinalValue*<br/>
Значение переменной анимации в конце перехода.

*dblFinalVelocity*<br/>
Скорость анимации переменной в конце перехода.

*dblAcceleration*<br/>
Ускорение анимации переменной во время перехода.

##  <a name="create"></a>  CParabolicTransitionFromAcceleration::Create

Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* /* not used */);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на библиотеку перехода, которая отвечает за создание стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.

##  <a name="m_dblacceleration"></a>  CParabolicTransitionFromAcceleration::m_dblAcceleration

Ускорение анимации переменной во время перехода.

```
DOUBLE m_dblAcceleration;
```

##  <a name="m_dblfinalvalue"></a>  CParabolicTransitionFromAcceleration::m_dblFinalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblfinalvelocity"></a>  CParabolicTransitionFromAcceleration::m_dblFinalVelocity

Скорость анимации переменной в конце перехода.

```
DOUBLE m_dblFinalVelocity;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
