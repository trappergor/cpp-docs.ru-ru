---
title: Класс CDiscreteTransition
ms.date: 11/04/2016
f1_keywords:
- CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::Create
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_delay
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_hold
helpviewer_keywords:
- CDiscreteTransition [MFC], CDiscreteTransition
- CDiscreteTransition [MFC], Create
- CDiscreteTransition [MFC], m_dblFinalValue
- CDiscreteTransition [MFC], m_delay
- CDiscreteTransition [MFC], m_hold
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
ms.openlocfilehash: 7087dfa13972737f0a1244d2cc9a7088b23dc184
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506856"
---
# <a name="cdiscretetransition-class"></a>Класс CDiscreteTransition

Инкапсулирует отдельный переход.

## <a name="syntax"></a>Синтаксис

```
class CDiscreteTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кдискрететранситион:: Кдискрететранситион](#cdiscretetransition)|Создает дискретный объект перехода и инициализирует его параметры.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кдискрететранситион:: Create](#create)|Вызывает библиотеку переходов для создания COM-объекта инкапсулированного перехода. (Переопределяет [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Кдискрететранситион:: m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|
|[Кдискрететранситион:: m_delay](#m_delay)|Промежуток времени, на который откладывается мгновенное переключение на окончательное значение.|
|[Кдискрететранситион:: m_hold](#m_hold)|Количество времени, на которое удерживается переменная в конечном значении.|

## <a name="remarks"></a>Примечания

Во время дискретного перехода переменная анимации остается в начальном значении для указанного времени задержки, затем переключается на указанное конечное значение и остается в этом значении в течение заданного времени удержания. Так как все переходы очищаются автоматически, рекомендуется выделять их с помощью оператора New. Инкапсулированный COM-объект Иуианиматионтранситион создается методом Каниматионконтроллер:: Аниматеграуп, пока он не будет равен NULL. Изменение переменных-членов после создания этого объекта COM не имеет силы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[кдискрететранситион](../../mfc/reference/cdiscretetransition-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="cdiscretetransition"></a>Кдискрететранситион:: Кдискрететранситион

Создает дискретный объект перехода и инициализирует его параметры.

```
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,
    DOUBLE dblFinalValue,
    UI_ANIMATION_SECONDS hold);
```

### <a name="parameters"></a>Параметры

*держивая*<br/>
Промежуток времени, на который откладывается мгновенное переключение на окончательное значение.

*дблфиналвалуе*<br/>
Значение переменной анимации в конце перехода.

*Нажмите*<br/>
Количество времени, на которое удерживается переменная в конечном значении.

##  <a name="create"></a>Кдискрететранситион:: Create

Вызывает библиотеку переходов для создания COM-объекта инкапсулированного перехода.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

*плибрари*<br/>
Указатель на [интерфейс иуианиматионтранситионлибрари](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если переход успешно создан; в противном случае — FALSE.

##  <a name="m_dblfinalvalue"></a>Кдискрететранситион:: m_dblFinalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_delay"></a>Кдискрететранситион:: m_delay

Промежуток времени, на который откладывается мгновенное переключение на окончательное значение.

```
UI_ANIMATION_SECONDS m_delay;
```

##  <a name="m_hold"></a>Кдискрететранситион:: m_hold

Количество времени, на которое удерживается переменная в конечном значении.

```
UI_ANIMATION_SECONDS m_hold;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
