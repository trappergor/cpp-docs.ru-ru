---
title: Класс CSinusoidalTransitionFromRange | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09c302ec414e26c71d8989bb6d624314c8eb6db4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="csinusoidaltransitionfromrange-class"></a>Класс CSinusoidalTransitionFromRange
Инкапсулирует переход в диапазоне синусоиды с заданной амплитудой колебаний.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSinusoidalTransitionFromRange : public CBaseTransition;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|Создает объект перехода.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::Create](#create)|Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::m_dblMaximumValue](#m_dblmaximumvalue)|Значение переменной анимации в пиковое значение синусоидальной wave.|  
|[CSinusoidalTransitionFromRange::m_dblMinimumValue](#m_dblminimumvalue)|Значение переменной анимации с помощью средства синусоидальной wave.|  
|[CSinusoidalTransitionFromRange::m_duration](#m_duration)|Продолжительность перехода.|  
|[CSinusoidalTransitionFromRange::m_period](#m_period)|Период колебаний из синусоидальной wave в секундах.|  
|[CSinusoidalTransitionFromRange::m_slope](#m_slope)|Наклон, то перед началом перехода.|  
  
## <a name="remarks"></a>Примечания  
 Между указанными минимальным и максимальным значениями на протяжении всего переход в диапазоне синусоиды изменяется значение переменной анимации. Наклон параметр используется для устранения неоднозначности между два возможных синус волны, указанных другими параметрами. Так как автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока, то возвращается значение NULL. Изменение переменных-членов, после создания этот объект COM не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="create"></a>  CSinusoidalTransitionFromRange::Create  
 Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Параметры  
 `pLibrary`  
 Указатель на переход библиотеку, которая отвечает за создание стандартной переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.  
  
##  <a name="csinusoidaltransitionfromrange"></a>  CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange  
 Создает объект перехода.  
  
```  
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblMinimumValue,  
    DOUBLE dblMaximumValue,  
    UI_ANIMATION_SECONDS period,  
    UI_ANIMATION_SLOPE slope);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Продолжительность перехода.  
  
 `dblMinimumValue`  
 Значение переменной анимации с помощью средства синусоидальной wave.  
  
 `dblMaximumValue`  
 Значение переменной анимации в пиковое значение синусоидальной wave.  
  
 `period`  
 Период колебаний из синусоидальной wave в секундах.  
  
 `slope`  
 Наклон, то перед началом перехода.  
  
##  <a name="m_dblmaximumvalue"></a>  CSinusoidalTransitionFromRange::m_dblMaximumValue  
 Значение переменной анимации в пиковое значение синусоидальной wave.  
  
```  
DOUBLE m_dblMaximumValue;  
```  
  
##  <a name="m_dblminimumvalue"></a>  CSinusoidalTransitionFromRange::m_dblMinimumValue  
 Значение переменной анимации с помощью средства синусоидальной wave.  
  
```  
DOUBLE m_dblMinimumValue;  
```  
  
##  <a name="m_duration"></a>  CSinusoidalTransitionFromRange::m_duration  
 Продолжительность перехода.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_period"></a>  CSinusoidalTransitionFromRange::m_period  
 Период колебаний из синусоидальной wave в секундах.  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
##  <a name="m_slope"></a>  CSinusoidalTransitionFromRange::m_slope  
 Наклон, то перед началом перехода.  
  
```  
UI_ANIMATION_SLOPE m_slope;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
