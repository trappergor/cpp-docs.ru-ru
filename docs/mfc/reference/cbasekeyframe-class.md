---
title: "Класс CBaseKeyFrame | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseKeyFrame
- afxanimationcontroller/CBaseKeyFrame
dev_langs:
- C++
helpviewer_keywords:
- CBaseKeyFrame class
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cfbaac379097c89b5dcb52fa36c0cd1f6e3d2c7f
ms.lasthandoff: 02/24/2017

---
# <a name="cbasekeyframe-class"></a>Класс CBaseKeyFrame
Реализует базовую функциональность ключевого кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Создает объект опорного кадра.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|Добавляет кадр в раскадровке.|  
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Возвращает базовое значение ключевого кадра.|  
|[CBaseKeyFrame::IsAdded](#isadded)|Указывает, был ли опорный кадр добавлен для раскадровки.|  
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|Указывает, следует ли добавить опорный кадр на раскадровку смещением или после перехода.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBaseKeyFrame::m_bAdded](#m_badded)|Указывает, был ли этот опорный кадр добавлен в раскадровку.|  
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Указывает, следует ли добавить этот опорный кадр для раскадровки со смещением от другого существующего опорного кадра или в конце некоторых перехода.|  
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Представляет ключевой кадр анимации Windows API. Опорный кадр не инициализирован присваивается определенное значение UI_ANIMATION_KEYFRAME_STORYBOARD_START.|  
  
## <a name="remarks"></a>Примечания  
 Инкапсулирует UI_ANIMATION_KEYFRAME переменной. Служит в качестве базового класса для реализации ключевого кадра. Опорный кадр представляет момент времени в пределах раскадровки и может использоваться для указания времени начала и окончания переходов. Существует два типа ключевых кадров - опорные кадры, добавляемый раскадровки с указанным смещением (по времени) или опорные кадры добавлен после указанного перехода. Так как длительность некоторые переходы не может быть известен до запуска анимации, фактические значения некоторых опорные кадры определяются только во время выполнения. Поскольку ключевые кадры могут зависеть переходов, зависящие в очередь опорные кадры, очень важно для предотвращения бесконечной рекурсии при построении цепочки опорного кадра.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseKeyFrame`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="a-nameaddtostoryboarda--cbasekeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>CBaseKeyFrame::AddToStoryboard  
 Добавляет кадр в раскадровке.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель раскадровки.  
  
 `bDeepAdd`  
 Если этот параметр имеет значение TRUE и опорный кадр добавлен зависит от других опорного кадра или перехода, этот метод пытается добавить этот кадр или перехода на раскадровку сначала.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если опорный кадр добавлен раскадровки успешно; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается, чтобы добавить опорный кадр на раскадровку.  
  
##  <a name="a-namecbasekeyframea--cbasekeyframecbasekeyframe"></a><a name="cbasekeyframe"></a>CBaseKeyFrame::CBaseKeyFrame  
 Создает объект опорного кадра.  
  
```  
CBaseKeyFrame();
```  
  
##  <a name="a-namegetanimationkeyframea--cbasekeyframegetanimationkeyframe"></a><a name="getanimationkeyframe"></a>CBaseKeyFrame::GetAnimationKeyframe  
 Возвращает базовое значение ключевого кадра.  
  
```  
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий кадр. Значение по умолчанию — UI_ANIMATION_KEYFRAME_STORYBOARD_START.  
  
### <a name="remarks"></a>Примечания  
 Это метод доступа к исходному значению ключевого кадра.  
  
##  <a name="a-nameisaddeda--cbasekeyframeisadded"></a><a name="isadded"></a>CBaseKeyFrame::IsAdded  
 Указывает, был ли опорный кадр добавлен для раскадровки.  
  
```  
BOOL IsAdded() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ключевой кадр добавляется в раскадровку; противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 В базовом классе IsAdded всегда возвращает значение TRUE, но он переопределен в производном классе.  
  
##  <a name="a-nameiskeyframeatoffseta--cbasekeyframeiskeyframeatoffset"></a><a name="iskeyframeatoffset"></a>CBaseKeyFrame::IsKeyframeAtOffset  
 Указывает, следует ли добавить опорный кадр на раскадровку смещением или после перехода.  
  
```  
BOOL IsKeyframeAtOffset() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если следует добавить опорный кадр раскадровки с заданным смещением. Значение FALSE, если раскадровка после некоторых перехода следует добавить опорный кадр.  
  
### <a name="remarks"></a>Примечания  
 Указывает, следует ли добавить опорный кадр на раскадровку смещением. В производном классе необходимо указать смещение или перехода.  
  
##  <a name="a-namembaddeda--cbasekeyframembadded"></a><a name="m_badded"></a>CBaseKeyFrame::m_bAdded  
 Указывает, был ли этот опорный кадр добавлен в раскадровку.  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="a-namembiskeyframeatoffseta--cbasekeyframembiskeyframeatoffset"></a><a name="m_biskeyframeatoffset"></a>CBaseKeyFrame::m_bIsKeyframeAtOffset  
 Указывает, следует ли добавить этот опорный кадр для раскадровки со смещением от другого существующего опорного кадра или в конце некоторых перехода.  
  
```  
BOOL m_bIsKeyframeAtOffset;  
```  
  
##  <a name="a-namemkeyframea--cbasekeyframemkeyframe"></a><a name="m_keyframe"></a>CBaseKeyFrame::m_keyframe  
 Представляет ключевой кадр анимации Windows API. Опорный кадр не инициализирован присваивается определенное значение UI_ANIMATION_KEYFRAME_STORYBOARD_START.  
  
```  
UI_ANIMATION_KEYFRAME m_keyframe;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

