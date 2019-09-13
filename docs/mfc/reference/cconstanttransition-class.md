---
title: Класс CConstantTransition
ms.date: 11/04/2016
f1_keywords:
- CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::Create
- AFXANIMATIONCONTROLLER/CConstantTransition::m_duration
helpviewer_keywords:
- CConstantTransition [MFC], CConstantTransition
- CConstantTransition [MFC], Create
- CConstantTransition [MFC], m_duration
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
ms.openlocfilehash: ccf08b309e64cd82215acb6032bc2a777f4c809a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507168"
---
# <a name="cconstanttransition-class"></a>Класс CConstantTransition

Инкапсулирует постоянный переход.

## <a name="syntax"></a>Синтаксис

```
class CConstantTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кконстанттранситион:: Кконстанттранситион](#cconstanttransition)|Создает объект перехода и инициализирует его длительность.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кконстанттранситион:: Create](#create)|Вызывает библиотеку переходов для создания COM-объекта инкапсулированного перехода. (Переопределяет [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Кконстанттранситион:: m_duration](#m_duration)|Длительность перехода.|

## <a name="remarks"></a>Примечания

Во время перехода константа значение переменной анимации остается на начальном значении в течение перехода. Так как все переходы очищаются автоматически, рекомендуется выделять их с помощью оператора New. Инкапсулированный COM-объект Иуианиматионтранситион создается методом Каниматионконтроллер:: Аниматеграуп, пока он не будет равен NULL. Изменение переменных-членов после создания этого объекта COM не имеет силы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CConstantTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="cconstanttransition"></a>Кконстанттранситион:: Кконстанттранситион

Создает объект перехода и инициализирует его длительность.

```
CConstantTransition (UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*длитель*<br/>
Длительность перехода.

##  <a name="create"></a>Кконстанттранситион:: Create

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

##  <a name="m_duration"></a>Кконстанттранситион:: m_duration

Длительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
