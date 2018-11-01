---
title: Класс CKeyFrame
ms.date: 11/04/2016
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
ms.openlocfilehash: b6ebe5ba78a259014f62bdf04f30e856a57f1aba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451081"
---
# <a name="ckeyframe-class"></a>Класс CKeyFrame

Представляет ключевой кадр анимации.

## <a name="syntax"></a>Синтаксис

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CKeyFrame::CKeyFrame](#ckeyframe)|Перегружен. Создает опорный кадр, зависящий от других опорного кадра.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Добавляет опорного кадра раскадровки. (Переопределяет [CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Добавляет кадр в раскадровку после перехода.|
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Добавляет опорный кадр на раскадровку смещением.|
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Возвращает указатель на опорного кадра, от которых зависит этот опорный кадр.|
|[CKeyFrame::GetOffset](#getoffset)|Возвращает смещение от других опорного кадра.|
|[CKeyFrame::GetTransition](#gettransition)|Возвращает указатель на переход, от которых зависит этот опорный кадр.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CKeyFrame::m_offset](#m_offset)|Задает смещение этот опорный кадр из хранящихся в m_pExistingKeyFrame опорного кадра.|
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Содержит указатель на существующий keframe. Этот ключевой кадр добавляется в раскадровку с m_offset существующий ключевой кадр.|
|[CKeyFrame::m_pTransition](#m_ptransition)|Содержит указатель на перехода, которая начинается с этого опорного кадра.|

## <a name="remarks"></a>Примечания

Этот класс реализует ключевой кадр анимации. Опорный кадр представляет момент времени в пределах раскадровки и может использоваться для укажите время начала и окончания переходов. Ключевой кадр может основываться на других опорных кадров и у него смещение (в секундах), или может основываться на переход и представляют на момент времени, когда заканчивается этот переход.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

##  <a name="addtostoryboard"></a>  CKeyFrame::AddToStoryboard

Добавляет опорного кадра раскадровки.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку.

*bDeepAdd*<br/>
Указывает, следует ли добавить опорный кадр или переход рекурсивно.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кадр был успешно добавлен.

### <a name="remarks"></a>Примечания

Этот метод добавляет опорный кадр на раскадровку. Если он зависит от других опорного кадра или перехода и bDeepAdd имеет значение TRUE, этот метод пытается рекурсивно добавьте их.

##  <a name="addtostoryboardaftertransition"></a>  CKeyFrame::AddToStoryboardAfterTransition

Добавляет кадр в раскадровку после перехода.

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку.

*bDeepAdd*<br/>
Указывает, следует ли добавить рекурсивно перехода.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кадр был успешно добавлен.

### <a name="remarks"></a>Примечания

Эта функция вызывается платформой, чтобы добавить опорный кадр в раскадровку после перехода.

##  <a name="addtostoryboardatoffset"></a>  CKeyFrame::AddToStoryboardAtOffset

Добавляет опорный кадр на раскадровку смещением.

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку.

*bDeepAdd*<br/>
Указывает ли добавить опорный кадр данного опорного кадра зависеть рекурсивно.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если кадр был успешно добавлен.

### <a name="remarks"></a>Примечания

Эта функция вызывается платформой, чтобы добавить опорный кадр на раскадровку смещением.

##  <a name="ckeyframe"></a>  CKeyFrame::CKeyFrame

Создает опорный кадр, зависящий от перехода.

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>Параметры

*pTransition*<br/>
Указатель на переход.

*параметром pKeyframe*<br/>
Указатель на основе опорных кадров.

*offset*<br/>
Смещение в секундах, от опорного кадра, заданного параметром pKeyframe.

### <a name="remarks"></a>Примечания

Сконструированный опорный кадр будет представлять на момент времени в раскадровке, после окончания указанного перехода.

##  <a name="getexistingkeyframe"></a>  CKeyFrame::GetExistingKeyframe

Возвращает указатель на опорного кадра, от которых зависит этот опорный кадр.

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>Возвращаемое значение

Допустимый указатель на кадр, или значение NULL, если этот кадр не зависит от других опорного кадра.

### <a name="remarks"></a>Примечания

Это метод доступа к опорного кадра, от которых зависит этот опорный кадр.

##  <a name="getoffset"></a>  CKeyFrame::GetOffset

Возвращает смещение от других опорного кадра.

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>Возвращаемое значение

Смещение в секундах от других опорного кадра.

### <a name="remarks"></a>Примечания

Этот метод должен вызываться для определения смещение в секундах от других опорного кадра.

##  <a name="gettransition"></a>  CKeyFrame::GetTransition

Возвращает указатель на переход, от которых зависит этот опорный кадр.

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>Возвращаемое значение

Допустимый указатель на переход, или значение NULL, если этот кадр не зависит от перехода.

### <a name="remarks"></a>Примечания

Это метод доступа к переход, от которых зависит этот опорный кадр.

##  <a name="m_offset"></a>  CKeyFrame::m_offset

Задает смещение этот опорный кадр из хранящихся в m_pExistingKeyFrame опорного кадра.

```
UI_ANIMATION_SECONDS m_offset;
```

##  <a name="m_pexistingkeyframe"></a>  CKeyFrame::m_pExistingKeyFrame

Содержит указатель на существующий keframe. Этот ключевой кадр добавляется в раскадровку с m_offset существующий ключевой кадр.

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

##  <a name="m_ptransition"></a>  CKeyFrame::m_pTransition

Содержит указатель на перехода, которая начинается с этого опорного кадра.

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
