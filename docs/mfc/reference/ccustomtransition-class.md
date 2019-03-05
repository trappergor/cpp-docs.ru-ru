---
title: Класс CCustomTransition
ms.date: 11/04/2016
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
ms.openlocfilehash: e0e5250b27ce6b902939ebcbfa03bf022a202788
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304019"
---
# <a name="ccustomtransition-class"></a>Класс CCustomTransition

Реализует пользовательский переход.

## <a name="syntax"></a>Синтаксис

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CCustomTransition::CCustomTransition](#ccustomtransition)|Создает объект пользовательский переход.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCustomTransition::Create](#create)|Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Задает начальное значение, которые будут применяться к переменной анимации, связанные с такого перехода.|
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Задает начальную скорость, который будет применяться к переменной анимации, связанные с такого перехода.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание:|
|----------|-----------------|
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|Указывает, задан ли параметр с SetInitialValue начальное значение.|
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|Указывает, задан ли параметр с SetInitialVelocity начальную скорость.|
|[CCustomTransition::m_initialValue](#m_initialvalue)|Сохраняет начальное значение.|
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|Хранит начальную скорость.|
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|Содержит указатель на пользовательские интерполятор.|

## <a name="remarks"></a>Примечания

Класс CCustomTransitions позволяет разработчикам реализовывать пользовательские переходов. Его создания, используется в качестве стандартных переход, но его конструктор принимает в качестве параметра указатель на пользовательские интерполятор. Выполните следующие действия, чтобы использовать пользовательские переходов. 1. Наследовать класс от CCustomInterpolator и реализуйте по крайней мере InterpolateValue метод. 2. Убедитесь, что время существования объекта пользовательских интерполятора должно быть длиннее продолжительность анимации места использования. 3. Создание экземпляра (с помощью оператора new) объекта CCustomTransition и передать указатель на пользовательские интерполятора в конструкторе. 4. Вызовите CCustomTransition::SetInitialValue и CCustomTransition::SetInitialVelocity, если эти параметры являются обязательными для пользовательской интерполяция. 5. Передайте указатель в пользовательский переход к методу AddTransition объекта анимации, значение которого для анимации с помощью пользовательского алгоритма. 6.  Когда следует изменить значение объекта анимации API анимации Windows вызывает InterpolateValue (и другие соответствующие методы) в CCustomInterpolator.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="ccustomtransition"></a>  CCustomTransition::CCustomTransition

Создает объект пользовательский переход.

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Параметры

*pInterpolator*<br/>
Указатель на пользовательские интерполятор.

##  <a name="create"></a>  CCustomTransition::Create

Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>Параметры

*pFactory*<br/>
Указатель на фабрику перехода, которая отвечает за создание пользовательских переходов.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Этот метод также можно задать начальное значение и начальную скорость для применения к переменной анимации, связанный с такого перехода. Для этого необходимо вызвать SetInitialValue и SetInitialVelocity, прежде чем платформа создает инкапсулированный перехода COM-объект (это происходит при вызове CAnimationController::AnimateGroup).

##  <a name="m_binitialvaluespecified"></a>  CCustomTransition::m_bInitialValueSpecified

Указывает, задан ли параметр с SetInitialValue начальное значение.

```
BOOL m_bInitialValueSpecified;
```

##  <a name="m_binitialvelocityspecified"></a>  CCustomTransition::m_bInitialVelocitySpecified

Указывает, задан ли параметр с SetInitialVelocity начальную скорость.

```
BOOL m_bInitialVelocitySpecified;
```

##  <a name="m_initialvalue"></a>  CCustomTransition::m_initialValue

Сохраняет начальное значение.

```
DOUBLE m_initialValue;
```

##  <a name="m_initialvelocity"></a>  CCustomTransition::m_initialVelocity

Хранит начальную скорость.

```
DOUBLE m_initialVelocity;
```

##  <a name="m_pinterpolator"></a>  CCustomTransition::m_pInterpolator

Содержит указатель на пользовательские интерполятор.

```
CCustomInterpolator* m_pInterpolator;
```

##  <a name="setinitialvalue"></a>  CCustomTransition::SetInitialValue

Задает начальное значение, которые будут применяться к переменной анимации, связанные с такого перехода.

```
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>Параметры

*Начальное значение*

##  <a name="setinitialvelocity"></a>  CCustomTransition::SetInitialVelocity

Задает начальную скорость, который будет применяться к переменной анимации, связанные с такого перехода.

```
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>Параметры

*initialVelocity*

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
