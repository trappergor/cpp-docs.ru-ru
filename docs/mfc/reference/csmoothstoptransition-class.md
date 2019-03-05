---
title: Класс CSmoothStopTransition
ms.date: 11/04/2016
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
ms.openlocfilehash: 89496c1b867d6fbb498f56271de7b45afef7edc3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290408"
---
# <a name="csmoothstoptransition-class"></a>Класс CSmoothStopTransition

Инкапсулирует переход с плавной остановкой.

## <a name="syntax"></a>Синтаксис

```
class CSmoothStopTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSmoothStopTransition::CSmoothStopTransition](#csmoothstoptransition)|Создает переход с плавной остановкой и инициализирует его Максимальная длительность и конечное значение.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CSmoothStopTransition::Create](#create)|Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CSmoothStopTransition::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|
|[CSmoothStopTransition::m_maximumDuration](#m_maximumduration)|Максимальная длительность перехода.|

## <a name="remarks"></a>Примечания

Переход с плавной остановкой замедляется, достигает заданного конечное значение, и достигается с помощью скорость в ноль. Продолжительность перехода определяется начальную скорость, разница между начальное и конечное значения и указанный максимальный период времени. Если ни одно решение, состоящее из одной параболической дуги, этот метод создает кубический переход. Так как автоматически удаляются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока то возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="create"></a>  CSmoothStopTransition::Create

Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на библиотеку перехода, которая отвечает за создание стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.

##  <a name="csmoothstoptransition"></a>  CSmoothStopTransition::CSmoothStopTransition

Создает переход с плавной остановкой и инициализирует его Максимальная длительность и конечное значение.

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Параметры

*maximumDuration*<br/>
Максимальная длительность перехода.

*dblFinalValue*<br/>
Значение переменной анимации в конце перехода.

##  <a name="m_dblfinalvalue"></a>  CSmoothStopTransition::m_dblFinalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_maximumduration"></a>  CSmoothStopTransition::m_maximumDuration

Максимальная длительность перехода.

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
