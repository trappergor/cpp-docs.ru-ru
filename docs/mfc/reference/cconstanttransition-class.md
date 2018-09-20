---
title: Класс CConstantTransition | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::Create
- AFXANIMATIONCONTROLLER/CConstantTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CConstantTransition [MFC], CConstantTransition
- CConstantTransition [MFC], Create
- CConstantTransition [MFC], m_duration
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d35234c6f39c95a879ae092f79b6357065216f7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446287"
---
# <a name="cconstanttransition-class"></a>Класс CConstantTransition

Инкапсулирует постоянный переход.

## <a name="syntax"></a>Синтаксис

```
class CConstantTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CConstantTransition::CConstantTransition](#cconstanttransition)|Создает объект перехода и инициализирует его длительность.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CConstantTransition::Create](#create)|Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CConstantTransition::m_duration](#m_duration)|Длительность перехода.|

## <a name="remarks"></a>Примечания

Во время перехода константа значение переменной анимации остается в начальное значение на протяжении перехода. Так как автоматически удаляются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока то возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CConstantTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="cconstanttransition"></a>  CConstantTransition::CConstantTransition

Создает объект перехода и инициализирует его длительность.

```
CConstantTransition (UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Длительность перехода.

##  <a name="create"></a>  CConstantTransition::Create

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

##  <a name="m_duration"></a>  CConstantTransition::m_duration

Длительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
