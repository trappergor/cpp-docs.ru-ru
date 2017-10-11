---
title: "CAccelerateDecelerateTransition Class1 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
dev_langs:
- C++
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 10712925645549f637ffea343e5ab6ce4220b5e3
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="cacceleratedeceleratetransition-class"></a>Класс CAccelerateDecelerateTransition
Реализует переход между ускорением и замедлением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Создает объект перехода.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::Create](#create)|Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Отношение значения времени, затраченный на ускорение длительности.|  
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Отношение значения времени, затраченный на замедление длительности.|  
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Продолжительность перехода.|  
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Значение переменной анимации в конце перехода.|  
  
## <a name="remarks"></a>Примечания  
 Во время ускорением-замедлением перехода, переменной анимации ускоряет и затем замедляет за период времени перехода, заканчивается в указанное значение. Можно управлять, насколько быстро переменную ускоряется и замедляется независимо от этого, указав другой ускорение и замедление коэффициенты. Если Начальная скорость равен нулю, ускорение составляет часть времени, на которое переменной затрачиваемых ускорению; Аналогичным образом с коэффициентом замедление. Если Начальная скорость не равно нулю, это доля времени между скорости достижения нуля и в конце перехода. Ускорение коэффициент и коэффициент замедление сумма должна составлять не более чем 1.0. Так как автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока, то возвращается значение NULL. Изменение переменных-членов, после создания этот объект COM не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CAccelerateDecelerateTransition`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="cacceleratedeceleratetransition"></a>CAccelerateDecelerateTransition::CAccelerateDecelerateTransition  
 Создает объект перехода.  
  
```  
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue,  
    DOUBLE accelerationRatio = 0.3,  
    DOUBLE decelerationRatio = 0.3);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Продолжительность перехода.  
  
 `finalValue`  
 Значение переменной анимации в конце перехода.  
  
 `accelerationRatio`  
 Отношение значения времени, затраченный на ускорение длительности.  
  
 `decelerationRatio`  
 Отношение значения времени, затраченный на замедление длительности.  
  
##  <a name="create"></a>CAccelerateDecelerateTransition::Create  
 Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* *\not used*\);
```  
  
### <a name="parameters"></a>Параметры  
`pLibrary`  
 Указатель на [IUIAnimationTransitionLibrary интерфейс](https://msdn.microsoft.com/library/windows/desktop/dd371897), который определяет библиотеку стандартных переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.  
  
##  <a name="m_accelerationratio"></a>CAccelerateDecelerateTransition::m_accelerationRatio  
 Отношение значения времени, затраченный на ускорение длительности.  
  
```  
DOUBLE m_accelerationRatio;  
```  
  
##  <a name="m_decelerationratio"></a>CAccelerateDecelerateTransition::m_decelerationRatio  
 Отношение значения времени, затраченный на замедление длительности.  
  
```  
DOUBLE m_decelerationRatio;  
```  
  
##  <a name="m_duration"></a>CAccelerateDecelerateTransition::m_duration  
 Продолжительность перехода.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>CAccelerateDecelerateTransition::m_finalValue  
 Значение переменной анимации в конце перехода.  
  
```  
DOUBLE m_finalValue;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

