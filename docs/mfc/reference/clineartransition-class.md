---
title: Класс CLinearTransition
ms.date: 11/04/2016
f1_keywords:
- CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::Create
- AFXANIMATIONCONTROLLER/CLinearTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransition::m_duration
helpviewer_keywords:
- CLinearTransition [MFC], CLinearTransition
- CLinearTransition [MFC], Create
- CLinearTransition [MFC], m_dblFinalValue
- CLinearTransition [MFC], m_duration
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
ms.openlocfilehash: 1a6348d1afd0117683bd31af61324b14e16f710c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505746"
---
# <a name="clineartransition-class"></a>Класс CLinearTransition

Инкапсулирует линейный переход.

## <a name="syntax"></a>Синтаксис

```
class CLinearTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Клинеартранситион:: Клинеартранситион](#clineartransition)|Создает объект линейного перехода и инициализирует его с помощью значения Duration и Final.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Клинеартранситион:: Create](#create)|Вызывает библиотеку переходов для создания COM-объекта инкапсулированного перехода. (Переопределяет [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Клинеартранситион:: m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|
|[Клинеартранситион:: m_duration](#m_duration)|Длительность перехода.|

## <a name="remarks"></a>Примечания

Во время линейного перехода значение переменной анимации переходит линейно от начального значения к указанному конечному значению. Так как все переходы очищаются автоматически, рекомендуется выделять их с помощью оператора New. Инкапсулированный COM-объект Иуианиматионтранситион создается методом Каниматионконтроллер:: Аниматеграуп, пока он не будет равен NULL. Изменение переменных-членов после создания этого объекта COM не имеет силы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[клинеартранситион](../../mfc/reference/clineartransition-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="clineartransition"></a>Клинеартранситион:: Клинеартранситион

Создает объект линейного перехода и инициализирует его с помощью значения Duration и Final.

```
CLinearTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Параметры

*длитель*<br/>
Длительность перехода.

*дблфиналвалуе*<br/>
Значение переменной анимации в конце перехода.

##  <a name="create"></a>Клинеартранситион:: Create

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

##  <a name="m_dblfinalvalue"></a>Клинеартранситион:: m_dblFinalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_duration"></a>Клинеартранситион:: m_duration

Длительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
