---
title: "Класс CKeyFrame | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CKeyFrame class
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d8ecff2e36148fb114ee708712b6e8bd0fe558ed
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ckeyframe-class"></a>Класс CKeyFrame
Представляет ключевой кадр анимации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](#ckeyframe)|Перегружен. Создает ключевой кадр, который зависит от других опорного кадра.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Добавляет раскадровку опорного кадра. (Переопределяет [CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Добавляет кадр на раскадровку после перехода.|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Добавляет кадр на раскадровку смещением.|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Возвращает указатель на ключевой кадр, от которых зависит этот кадр.|  
|[CKeyFrame::GetOffset](#getoffset)|Возвращает смещение от других опорного кадра.|  
|[CKeyFrame::GetTransition](#gettransition)|Возвращает указатель на переход, от которых зависит этот кадр.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|Задает смещение этот кадр из опорный кадр, хранящиеся в m_pExistingKeyFrame.|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Хранит указатель на существующих keframe. Этот ключевой кадр добавляется раскадровки с m_offset существующий ключевой кадр.|  
|[CKeyFrame::m_pTransition](#m_ptransition)|Хранит указатель для перехода, которая начинается с этой ключевой кадр.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс реализует кадр анимации. Опорный кадр представляет момент времени в пределах раскадровки и может использоваться для указания времени начала и окончания переходов. Опорный кадр может основываться на другой кадр и смещение (в секундах), или могут быть основаны на переход и представляют на момент времени, когда заканчивается этот переход.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>CKeyFrame::AddToStoryboard  
 Добавляет раскадровку опорного кадра.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель раскадровки.  
  
 `bDeepAdd`  
 Указывает, следует ли добавить опорный кадр или переход рекурсивно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ключевой кадр был успешно добавлен.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет опорный кадр на раскадровку. Если он зависит от других опорного кадра или перехода и bDeepAdd имеет значение TRUE, этот метод пытается рекурсивно добавьте их.  
  
##  <a name="addtostoryboardaftertransition"></a>CKeyFrame::AddToStoryboardAfterTransition  
 Добавляет кадр на раскадровку после перехода.  
  
```  
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель раскадровки.  
  
 `bDeepAdd`  
 Указывает, следует ли добавить рекурсивно перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ключевой кадр был успешно добавлен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается платформой, чтобы добавить опорный кадр на раскадровку после перехода.  
  
##  <a name="addtostoryboardatoffset"></a>CKeyFrame::AddToStoryboardAtOffset  
 Добавляет кадр на раскадровку смещением.  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Параметры  
 `pStoryboard`  
 Указатель раскадровки.  
  
 `bDeepAdd`  
 Указывает ли добавить опорный кадр этот кадр зависят от рекурсивно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ключевой кадр был успешно добавлен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается платформой, чтобы добавить опорный кадр на раскадровку смещением.  
  
##  <a name="ckeyframe"></a>CKeyFrame::CKeyFrame  
 Создает ключевой кадр, который зависит от перехода.  
  
```  
CKeyFrame(CBaseTransition* pTransition);

 
CKeyFrame(
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>Параметры  
 `pTransition`  
 Указатель на переход.  
  
 `pKeyframe`  
 Указатель опорного кадра.  
  
 `offset`  
 Смещение в секундах от определяемого pKeyframe опорного кадра.  
  
### <a name="remarks"></a>Примечания  
 Сконструированный опорный кадр будет представлять на момент времени в раскадровке, после окончания указанного перехода.  
  
##  <a name="getexistingkeyframe"></a>CKeyFrame::GetExistingKeyframe  
 Возвращает указатель на ключевой кадр, от которых зависит этот кадр.  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель опорного кадра, или значение NULL, если этот кадр не зависит от других опорного кадра.  
  
### <a name="remarks"></a>Примечания  
 Это метод доступа для опорного кадра, от которых зависит этот кадр.  
  
##  <a name="getoffset"></a>CKeyFrame::GetOffset  
 Возвращает смещение от других опорного кадра.  
  
```  
UI_ANIMATION_SECONDS GetOffset();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Смещение в секундах от других опорного кадра.  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться для определения смещения в секундах от других опорного кадра.  
  
##  <a name="gettransition"></a>CKeyFrame::GetTransition  
 Возвращает указатель на переход, от которых зависит этот кадр.  
  
```  
CBaseTransition* GetTransition();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель для перехода или значение NULL, если этот кадр не зависит от перехода.  
  
### <a name="remarks"></a>Примечания  
 Это метод доступа для перехода, от которых зависит этот кадр.  
  
##  <a name="m_offset"></a>CKeyFrame::m_offset  
 Задает смещение этот кадр из опорный кадр, хранящиеся в m_pExistingKeyFrame.  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="m_pexistingkeyframe"></a>CKeyFrame::m_pExistingKeyFrame  
 Хранит указатель на существующих keframe. Этот ключевой кадр добавляется раскадровки с m_offset существующий ключевой кадр.  
  
```  
CBaseKeyFrame* m_pExistingKeyFrame;  
```  
  
##  <a name="m_ptransition"></a>CKeyFrame::m_pTransition  
 Хранит указатель для перехода, которая начинается с этой ключевой кадр.  
  
```  
CBaseTransition* m_pTransition;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

