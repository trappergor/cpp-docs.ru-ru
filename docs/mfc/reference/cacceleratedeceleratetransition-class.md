---
title: Класс CAccelerateDecelerateTransition
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: 1e55e81b4d9b5c324f86bfd141b74d9faa362d94
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507741"
---
# <a name="cacceleratedeceleratetransition-class"></a>Класс CAccelerateDecelerateTransition

Реализует переход между ускорением и замедлением.

## <a name="syntax"></a>Синтаксис

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Какцелератедецелератетранситион:: Какцелератедецелератетранситион](#cacceleratedeceleratetransition)|Конструирует объект перехода.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Какцелератедецелератетранситион:: Create](#create)|Вызывает библиотеку переходов для создания COM-объекта инкапсулированного перехода. (Переопределяет [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Какцелератедецелератетранситион:: m_accelerationRatio](#m_accelerationratio)|Отношение времени, затраченного на время, которое ускоряется до длительности.|
|[Какцелератедецелератетранситион:: m_decelerationRatio](#m_decelerationratio)|Отношение времени, затраченного на замедление, к длительности.|
|[Какцелератедецелератетранситион:: m_duration](#m_duration)|Длительность перехода.|
|[Какцелератедецелератетранситион:: m_finalValue](#m_finalvalue)|Значение переменной анимации в конце перехода.|

## <a name="remarks"></a>Примечания

Во время перехода с ускорением от ускорение переменная анимации ускоряется, а затем замедляется на протяжении перехода, заканчивая указанным значением. Можно управлять тем, насколько быстро переменная ускоряется и замедляется независимо друг от друга, указывая различные коэффициенты ускорения и замедления. Если начальная скорость равна нулю, коэффициент ускорения — это доля продолжительности, которую переменная будет тратить на ускорение. Аналогично соотношение замедления. Если начальная скорость не равна нулю, то это доля времени между достижением нуля и концом перехода. Коэффициент ускорения и коэффициент замедления должен суммироваться максимум до 1,0. Так как все переходы очищаются автоматически, рекомендуется выделять их с помощью оператора New. Инкапсулированный COM-объект Иуианиматионтранситион создается методом Каниматионконтроллер:: Аниматеграуп, пока он не будет равен NULL. Изменение переменных-членов после создания этого объекта COM не имеет силы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="cacceleratedeceleratetransition"></a>Какцелератедецелератетранситион:: Какцелератедецелератетранситион

Конструирует объект перехода.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>Параметры

*длитель*<br/>
Длительность перехода.

*финалвалуе*<br/>
Значение переменной анимации в конце перехода.

*accelerationRatio*<br/>
Отношение времени, затраченного на время, которое ускоряется до длительности.

*decelerationRatio*<br/>
Отношение времени, затраченного на замедление, к длительности.

##  <a name="create"></a>Какцелератедецелератетранситион:: Create

Вызывает библиотеку переходов для создания COM-объекта инкапсулированного перехода.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>Параметры

*плибрари*<br/>
Указатель на [интерфейс иуианиматионтранситионлибрари](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход успешно создан; в противном случае — FALSE.

##  <a name="m_accelerationratio"></a>Какцелератедецелератетранситион:: m_accelerationRatio

Отношение времени, затраченного на время, которое ускоряется до длительности.

```
DOUBLE m_accelerationRatio;
```

##  <a name="m_decelerationratio"></a>Какцелератедецелератетранситион:: m_decelerationRatio

Отношение времени, затраченного на замедление, к длительности.

```
DOUBLE m_decelerationRatio;
```

##  <a name="m_duration"></a>Какцелератедецелератетранситион:: m_duration

Длительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>Какцелератедецелератетранситион:: m_finalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
