---
title: Класс CLinearTransitionFromSpeed
ms.date: 11/04/2016
f1_keywords:
- CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::Create
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblSpeed
helpviewer_keywords:
- CLinearTransitionFromSpeed [MFC], CLinearTransitionFromSpeed
- CLinearTransitionFromSpeed [MFC], Create
- CLinearTransitionFromSpeed [MFC], m_dblFinalValue
- CLinearTransitionFromSpeed [MFC], m_dblSpeed
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
ms.openlocfilehash: 50c958a092478f4b9ec4e94f9e5e973a74c334c2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505715"
---
# <a name="clineartransitionfromspeed-class"></a>Класс CLinearTransitionFromSpeed

Инкапсулирует переход с линейной скоростью.

## <a name="syntax"></a>Синтаксис

```
class CLinearTransitionFromSpeed : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Клинеартранситионфромспид:: Клинеартранситионфромспид](#clineartransitionfromspeed)|Создает объект перехода линейной скорости и инициализирует его с помощью скорости и конечного значения.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Клинеартранситионфромспид:: Create](#create)|Вызывает библиотеку переходов для создания COM-объекта инкапсулированного перехода. (Переопределяет [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Клинеартранситионфромспид:: m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|
|[Клинеартранситионфромспид:: m_dblSpeed](#m_dblspeed)|Абсолютное значение скорости переменной.|

## <a name="remarks"></a>Примечания

При переходе на линейную скорость значение переменной анимации изменяется с заданной скоростью. Длительность перехода определяется разницей между начальным значением и указанным окончательным значением. Так как все переходы очищаются автоматически, рекомендуется выделять их с помощью оператора New. Инкапсулированный COM-объект Иуианиматионтранситион создается методом Каниматионконтроллер:: Аниматеграуп, пока он не будет равен NULL. Изменение переменных-членов после создания этого объекта COM не имеет силы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[клинеартранситионфромспид](../../mfc/reference/clineartransitionfromspeed-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="clineartransitionfromspeed"></a>Клинеартранситионфромспид:: Клинеартранситионфромспид

Создает объект перехода линейной скорости и инициализирует его с помощью скорости и конечного значения.

```
CLinearTransitionFromSpeed(
    DOUBLE dblSpeed,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Параметры

*дблспид*<br/>
Абсолютное значение скорости переменной.

*дблфиналвалуе*<br/>
Значение переменной анимации в конце перехода.

##  <a name="create"></a>Клинеартранситионфромспид:: Create

Вызывает библиотеку переходов для создания COM-объекта инкапсулированного перехода.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*плибрари*<br/>
Указатель на [интерфейс иуианиматионтранситионлибрари](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход успешно создан; в противном случае — FALSE.

##  <a name="m_dblfinalvalue"></a>Клинеартранситионфромспид:: m_dblFinalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblspeed"></a>Клинеартранситионфромспид:: m_dblSpeed

Абсолютное значение скорости переменной.

```
DOUBLE m_dblSpeed;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
