---
title: Класс CReversalTransition | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::Create
- AFXANIMATIONCONTROLLER/CReversalTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CReversalTransition [MFC], CReversalTransition
- CReversalTransition [MFC], Create
- CReversalTransition [MFC], m_duration
ms.assetid: e89516be-2d07-4885-95a8-fc278f46e3ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 393c0ed7c9d1c5715528468e0c611ae399fbadf6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431506"
---
# <a name="creversaltransition-class"></a>Класс CReversalTransition

Инкапсулирует обратный переход.

## <a name="syntax"></a>Синтаксис

```
class CReversalTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CReversalTransition::CReversalTransition](#creversaltransition)|Создает объект обратный порядок перехода и инициализирует его длительность.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CReversalTransition::Create](#create)|Вызывает переход библиотеку для создания инкапсулированный перехода COM-объекта. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CReversalTransition::m_duration](#m_duration)|Длительность перехода.|

## <a name="remarks"></a>Примечания

Обратный переход плавно изменяет направление в течение заданного периода. Конечное значение будет таким же, как начальное значение и Конечная скорость будет начальную скорость с противоположным знаком. Так как автоматически удаляются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока то возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CReversalTransition](../../mfc/reference/creversaltransition-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="create"></a>  CReversalTransition::Create

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

##  <a name="creversaltransition"></a>  CReversalTransition::CReversalTransition

Создает объект обратный порядок перехода и инициализирует его длительность.

```
CReversalTransition(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Длительность перехода.

##  <a name="m_duration"></a>  CReversalTransition::m_duration

Длительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
