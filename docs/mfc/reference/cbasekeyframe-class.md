---
title: Класс CBaseKeyFrame
ms.date: 11/04/2016
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
ms.openlocfilehash: d36c924d30bd728fcd54b6cdf6805ade25e20b5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218410"
---
# <a name="cbasekeyframe-class"></a>Класс CBaseKeyFrame

Реализует базовую функциональность ключевого кадра.

## <a name="syntax"></a>Синтаксис

```
class CBaseKeyFrame : public CObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Создает объект опорного кадра.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|Добавляет кадр в раскадровку.|
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Возвращает базовое значение опорного кадра.|
|[CBaseKeyFrame::IsAdded](#isadded)|Указывает, был ли опорный кадр добавлен в раскадровку.|
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Указывает, следует ли добавлять опорный кадр на раскадровку смещением, или после перехода.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CBaseKeyFrame::m_bAdded](#m_badded)|Указывает, был ли этот опорный кадр добавлен раскадровки.|
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Указывает, следует ли добавлять этот опорный кадр на раскадровку со смещением относительно другого существующего опорного кадра, или в конце некоторых перехода.|
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Представляет ключевой кадр анимации API Windows. Опорный кадр не инициализирован присваивается определенное значение UI_ANIMATION_KEYFRAME_STORYBOARD_START.|

## <a name="remarks"></a>Примечания

Инкапсулирует UI_ANIMATION_KEYFRAME переменной. Служит в качестве базового класса для реализации опорного кадра. Опорный кадр представляет момент времени в пределах раскадровки и может использоваться для укажите время начала и окончания переходов. Существует два типа ключевых кадров - опорные кадры, добавлен в раскадровку с указанным смещением (по времени) или опорные кадры, добавленные после указанного перехода. Так как длительность одни переходы не может быть известен до запуска анимации, фактические значения некоторых опорные кадры определяются только во время выполнения. Поскольку опорные кадры могут зависеть переходов, зависящие в очередь опорные кадры, очень важно для предотвращения бесконечной рекурсии при построении цепочки опорного кадра.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="addtostoryboard"></a>  CBaseKeyFrame::AddToStoryboard

Добавляет кадр в раскадровку.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку.

*bDeepAdd*<br/>
Если этот параметр имеет значение TRUE, добавляемый опорный кадр зависит от того, некоторые опорного кадра или перехода, этот метод пытается добавить данного опорного кадра или перехода в раскадровку сначала.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кадр был добавлен в раскадровку успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается, чтобы добавить опорный кадр на раскадровку.

##  <a name="cbasekeyframe"></a>  CBaseKeyFrame::CBaseKeyFrame

Создает объект опорного кадра.

```
CBaseKeyFrame();
```

##  <a name="getanimationkeyframe"></a>  CBaseKeyFrame::GetAnimationKeyframe

Возвращает базовое значение опорного кадра.

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий кадр. Значение по умолчанию — UI_ANIMATION_KEYFRAME_STORYBOARD_START.

### <a name="remarks"></a>Примечания

Это метод доступа к исходному значению, опорный кадр.

##  <a name="isadded"></a>  CBaseKeyFrame::IsAdded

Указывает, был ли опорный кадр добавлен в раскадровку.

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если опорный кадр добавлен раскадровки; противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

В базовом классе IsAdded всегда возвращает значение TRUE, но он переопределен в производных классах.

##  <a name="iskeyframeatoffset"></a>  CBaseKeyFrame::IsKeyframeAtOffset

Указывает, следует ли добавлять опорный кадр на раскадровку смещением, или после перехода.

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если следует добавить опорный кадр на раскадровку с указанным смещением. Значение FALSE, если опорный кадр следует добавить в раскадровку после некоторых перехода.

### <a name="remarks"></a>Примечания

Указывает, следует ли добавлять опорный кадр на раскадровку смещением. В производном классе необходимо указать смещение или перехода.

##  <a name="m_badded"></a>  CBaseKeyFrame::m_bAdded

Указывает, был ли этот опорный кадр добавлен раскадровки.

```
BOOL m_bAdded;
```

##  <a name="m_biskeyframeatoffset"></a>  CBaseKeyFrame::m_bIsKeyframeAtOffset

Указывает, следует ли добавлять этот опорный кадр на раскадровку со смещением относительно другого существующего опорного кадра, или в конце некоторых перехода.

```
BOOL m_bIsKeyframeAtOffset;
```

##  <a name="m_keyframe"></a>  CBaseKeyFrame::m_keyframe

Представляет ключевой кадр анимации API Windows. Опорный кадр не инициализирован присваивается определенное значение UI_ANIMATION_KEYFRAME_STORYBOARD_START.

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
