---
title: Класс CKeyFrame | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56fa354a46e40704ac063791931ca01d1386a558
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038462"
---
# <a name="ckeyframe-class"></a>Класс CKeyFrame
Представляет ключевой кадр анимации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](#ckeyframe)|Перегружен. Создает опорный кадр, зависящий от других опорных кадров.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|Добавляет опорный кадр в раскадровку. (Переопределяет [CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|Добавляет кадр в раскадровку после перехода.|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|Добавляет кадр в раскадровку смещением.|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Возвращает указатель на ключевой кадр, от которых зависит этот кадр.|  
|[CKeyFrame::GetOffset](#getoffset)|Возвращает смещение от других опорных кадров.|  
|[CKeyFrame::GetTransition](#gettransition)|Возвращает указатель на переход, от которых зависит этот кадр.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|Задает смещение данного опорного кадра из ключевого кадра, хранящиеся в m_pExistingKeyFrame.|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Содержит указатель на существующий keframe. Этот кадр добавляется в раскадровку с m_offset на существующий ключевой кадр.|  
|[CKeyFrame::m_pTransition](#m_ptransition)|Хранит указатель перехода, которая начинается с этого ключевого кадра.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс реализует ключевой кадр анимации. Опорный кадр представляет момент времени в пределах раскадровки и может использоваться для указания времени начала и окончания переходов. Опорный кадр может основываться на других опорных кадров и смещение (в секундах) из него, или может быть основана на переход и представляют на момент времени, когда заканчивается этот переход.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>  CKeyFrame::AddToStoryboard  
 Добавляет опорный кадр в раскадровку.  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Параметры  
 *pStoryboard*  
 Указатель на раскадровку.  
  
 *bDeepAdd*  
 Указывает, следует ли добавить ключевой кадр или переход рекурсивно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кадр был успешно добавлен.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет опорный кадр в раскадровку. Если он зависит от другой кадр или перехода и bDeepAdd имеет значение TRUE, этот метод пытается добавить их рекурсивно.  
  
##  <a name="addtostoryboardaftertransition"></a>  CKeyFrame::AddToStoryboardAfterTransition  
 Добавляет кадр в раскадровку после перехода.  
  
```  
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Параметры  
 *pStoryboard*  
 Указатель на раскадровку.  
  
 *bDeepAdd*  
 Указывает, следует ли добавить рекурсивно перехода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кадр был успешно добавлен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается платформой для добавления ключевого кадра в раскадровку после перехода.  
  
##  <a name="addtostoryboardatoffset"></a>  CKeyFrame::AddToStoryboardAtOffset  
 Добавляет кадр в раскадровку смещением.  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>Параметры  
 *pStoryboard*  
 Указатель на раскадровку.  
  
 *bDeepAdd*  
 Указывает, зависят ли от Добавление опорный кадр данного опорного кадра рекурсивно.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если кадр был успешно добавлен.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается платформой, чтобы добавить опорный кадр в раскадровку смещением.  
  
##  <a name="ckeyframe"></a>  CKeyFrame::CKeyFrame  
 Создает опорный кадр, зависящий от перехода.  
  
```  
CKeyFrame(CBaseTransition* pTransition);

 
CKeyFrame(
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>Параметры  
 *pTransition*  
 Указатель на переход.  
  
 *параметром pKeyframe*  
 Указатель на опорный кадр.  
  
 *offset*  
 Смещение в секундах от ключевого кадра, заданного параметром pKeyframe.  
  
### <a name="remarks"></a>Примечания  
 Сконструированный опорный кадр будет представлять на момент времени в раскадровку после окончания указанного перехода.  
  
##  <a name="getexistingkeyframe"></a>  CKeyFrame::GetExistingKeyframe  
 Возвращает указатель на ключевой кадр, от которых зависит этот кадр.  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель опорных кадров, или значение NULL, если этот кадр не зависит от других опорных кадров.  
  
### <a name="remarks"></a>Примечания  
 Это метод доступа для опорного кадра, от которых зависит этот кадр.  
  
##  <a name="getoffset"></a>  CKeyFrame::GetOffset  
 Возвращает смещение от других опорных кадров.  
  
```  
UI_ANIMATION_SECONDS GetOffset();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Смещение в секундах от других опорных кадров.  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться для определения смещение в секундах от других опорных кадров.  
  
##  <a name="gettransition"></a>  CKeyFrame::GetTransition  
 Возвращает указатель на переход, от которых зависит этот кадр.  
  
```  
CBaseTransition* GetTransition();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Допустимый указатель перехода, или значение NULL, если этот кадр не зависит от перехода.  
  
### <a name="remarks"></a>Примечания  
 Это метод доступа для перехода, от которых зависит этот кадр.  
  
##  <a name="m_offset"></a>  CKeyFrame::m_offset  
 Задает смещение данного опорного кадра из ключевого кадра, хранящиеся в m_pExistingKeyFrame.  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="m_pexistingkeyframe"></a>  CKeyFrame::m_pExistingKeyFrame  
 Содержит указатель на существующий keframe. Этот кадр добавляется в раскадровку с m_offset на существующий ключевой кадр.  
  
```  
CBaseKeyFrame* m_pExistingKeyFrame;  
```  
  
##  <a name="m_ptransition"></a>  CKeyFrame::m_pTransition  
 Хранит указатель перехода, которая начинается с этого ключевого кадра.  
  
```  
CBaseTransition* m_pTransition;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
