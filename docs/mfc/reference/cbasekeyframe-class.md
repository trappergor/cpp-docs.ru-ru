---
title: Класс CBaseKeyFrame | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f538874b1690be920e9c7a3b3f494ca6851c532
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cbasekeyframe-class"></a>Класс CBaseKeyFrame
Реализует базовую функциональность ключевого кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Создает объект опорного кадра.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|Добавляет кадр в раскадровку.|  
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Возвращает базовое значение ключевого кадра.|  
|[CBaseKeyFrame::IsAdded](#isadded)|Указывает, были ли добавлены опорный кадр в раскадровку.|  
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Указывает, следует ли добавить ключевой кадр в раскадровку позиции или после перехода.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[CBaseKeyFrame::m_bAdded](#m_badded)|Указывает, был ли этот кадр добавлен раскадровки.|  
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Указывает, следует ли добавить в раскадровку со смещением от другой существующий ключевой кадр, или в конце некоторых перехода данного опорного кадра.|  
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Представляет ключевой кадр анимации Windows API. Опорный кадр не инициализирован присваивается определенное значение UI_ANIMATION_KEYFRAME_STORYBOARD_START.|  
  
## <a name="remarks"></a>Примечания  
 Инкапсулирует UI_ANIMATION_KEYFRAME переменной. Служит в качестве базового класса для любой реализации опорного кадра. Опорный кадр представляет момент времени в пределах раскадровки и может использоваться для указания времени начала и окончания переходов. Существует два типа ключевых кадров - опорные кадры, которые добавлены в раскадровку с указанным смещением (по времени) или опорные кадры, добавлены после указанного перехода. Так как длительность некоторые переходы не может быть известен до начала анимации, фактические значения некоторых ключевых кадров определяются только во время выполнения. Поскольку опорные кадры могут зависеть переходов, зависящие от в очередь опорные кадры, очень важно для предотвращения бесконечной рекурсии при построении цепочки опорного кадра.  
  
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
 `pStoryboard`  
 Указатель на раскадровку.  
  
 `bDeepAdd`  
 Если этот параметр имеет значение TRUE и добавляемый ключевой кадр зависит от другой кадр или перехода, этот метод пытается добавить данного ключевого кадра или перехода на раскадровку сначала.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кадр был добавлен в раскадровку успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается для добавления ключевого кадра в раскадровку.  
  
##  <a name="cbasekeyframe"></a>  CBaseKeyFrame::CBaseKeyFrame  
 Создает объект опорного кадра.  
  
```  
CBaseKeyFrame();
```  
  
##  <a name="getanimationkeyframe"></a>  CBaseKeyFrame::GetAnimationKeyframe  
 Возвращает базовое значение ключевого кадра.  
  
```  
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий кадр. Значение по умолчанию — UI_ANIMATION_KEYFRAME_STORYBOARD_START.  
  
### <a name="remarks"></a>Примечания  
 Это метод доступа к исходному значению ключевого кадра.  
  
##  <a name="isadded"></a>  CBaseKeyFrame::IsAdded  
 Указывает, были ли добавлены опорный кадр в раскадровку.  
  
```  
BOOL IsAdded() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кадр добавляется в раскадровку; противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 В базовом классе IsAdded всегда возвращает значение TRUE, но он переопределяется в производных классах.  
  
##  <a name="iskeyframeatoffset"></a>  CBaseKeyFrame::IsKeyframeAtOffset  
 Указывает, следует ли добавить ключевой кадр в раскадровку позиции или после перехода.  
  
```  
BOOL IsKeyframeAtOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ключевой кадр следует добавить в раскадровку некоторые указанной позиции. Значение FALSE, если ключевой кадр следует добавить в раскадровку после некоторых перехода.  
  
### <a name="remarks"></a>Примечания  
 Указывает, следует ли добавить ключевой кадр в раскадровку смещением. В производном классе необходимо указать смещение или перехода.  
  
##  <a name="m_badded"></a>  CBaseKeyFrame::m_bAdded  
 Указывает, был ли этот кадр добавлен раскадровки.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_biskeyframeatoffset"></a>  CBaseKeyFrame::m_bIsKeyframeAtOffset  
 Указывает, следует ли добавить в раскадровку со смещением от другой существующий ключевой кадр, или в конце некоторых перехода данного опорного кадра.  
  
```  
BOOL m_bIsKeyframeAtOffset;  
```  
  
##  <a name="m_keyframe"></a>  CBaseKeyFrame::m_keyframe  
 Представляет ключевой кадр анимации Windows API. Опорный кадр не инициализирован присваивается определенное значение UI_ANIMATION_KEYFRAME_STORYBOARD_START.  
  
```  
UI_ANIMATION_KEYFRAME m_keyframe;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
