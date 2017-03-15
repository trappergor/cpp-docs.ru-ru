---
title: "Класс CParabolicTransitionFromAcceleration | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration
dev_langs:
- C++
helpviewer_keywords:
- CParabolicTransitionFromAcceleration class
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f0d3089a01cd244851be3d4bdf0453101a9c8274
ms.lasthandoff: 02/24/2017

---
# <a name="cparabolictransitionfromacceleration-class"></a>Класс CParabolicTransitionFromAcceleration
Инкапсулирует переход с параболическим ускорением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CParabolicTransitionFromAcceleration : public CBaseTransition;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|Переход с параболическим ускорением создает и инициализирует его с указанными параметрами.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::Create](#create)|Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::m_dblAcceleration](#m_dblacceleration)|Ускорение анимации переменной во время перехода.|  
|[CParabolicTransitionFromAcceleration::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|  
|[CParabolicTransitionFromAcceleration::m_dblFinalVelocity](#m_dblfinalvelocity)|Скоростью переменной анимации в конце перехода.|  
  
## <a name="remarks"></a>Примечания  
 Во время перехода параболическим ускорением значение переменной анимации изменяется от начального значения окончательное значение заканчивается на указанной скорости. Можно контролировать, как быстро переменная достигает окончательное значение, указав скорость ускорение. Поскольку автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока затем возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="a-namecparabolictransitionfromaccelerationa--cparabolictransitionfromaccelerationcparabolictransitionfromacceleration"></a><a name="cparabolictransitionfromacceleration"></a>CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration  
 Переход с параболическим ускорением создает и инициализирует его с указанными параметрами.  
  
```  
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,  
    DOUBLE dblFinalVelocity,  
    DOUBLE dblAcceleration);
```  
  
### <a name="parameters"></a>Параметры  
 `dblFinalValue`  
 Значение переменной анимации в конце перехода.  
  
 `dblFinalVelocity`  
 Скоростью переменной анимации в конце перехода.  
  
 `dblAcceleration`  
 Ускорение анимации переменной во время перехода.  
  
##  <a name="a-namecreatea--cparabolictransitionfromaccelerationcreate"></a><a name="create"></a>CParabolicTransitionFromAcceleration::Create  
 Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* /* not used */);
```  
  
### <a name="parameters"></a>Параметры  
 `pLibrary`  
 Указатель на переход библиотеки, которая отвечает за создание стандартной переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход создано успешно; в противном случае — значение FALSE.  
  
##  <a name="a-namemdblaccelerationa--cparabolictransitionfromaccelerationmdblacceleration"></a><a name="m_dblacceleration"></a>CParabolicTransitionFromAcceleration::m_dblAcceleration  
 Ускорение анимации переменной во время перехода.  
  
```  
DOUBLE m_dblAcceleration;  
```  
  
##  <a name="a-namemdblfinalvaluea--cparabolictransitionfromaccelerationmdblfinalvalue"></a><a name="m_dblfinalvalue"></a>CParabolicTransitionFromAcceleration::m_dblFinalValue  
 Значение переменной анимации в конце перехода.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="a-namemdblfinalvelocitya--cparabolictransitionfromaccelerationmdblfinalvelocity"></a><a name="m_dblfinalvelocity"></a>CParabolicTransitionFromAcceleration::m_dblFinalVelocity  
 Скоростью переменной анимации в конце перехода.  
  
```  
DOUBLE m_dblFinalVelocity;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

