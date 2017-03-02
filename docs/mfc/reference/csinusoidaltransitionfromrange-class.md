---
title: "Класс CSinusoidalTransitionFromRange | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromRange class
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
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
ms.openlocfilehash: f9dd0e236207c0b4139de42f4c616aaad9dcad28
ms.lasthandoff: 02/24/2017

---
# <a name="csinusoidaltransitionfromrange-class"></a>Класс CSinusoidalTransitionFromRange
Инкапсулирует переход в диапазоне синусоиды с заданной амплитудой колебаний.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSinusoidalTransitionFromRange : public CBaseTransition;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|Создает объект перехода.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::Create](#create)|Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSinusoidalTransitionFromRange::m_dblMaximumValue](#m_dblmaximumvalue)|Значение переменной анимации пик синусоиды wave.|  
|[CSinusoidalTransitionFromRange::m_dblMinimumValue](#m_dblminimumvalue)|Значение переменной анимации с помощью синусоиды wave.|  
|[CSinusoidalTransitionFromRange::m_duration](#m_duration)|Длительность перехода.|  
|[CSinusoidalTransitionFromRange::m_period](#m_period)|Период колебаний из синусоиды wave в секундах.|  
|[CSinusoidalTransitionFromRange::m_slope](#m_slope)|Наклон в начале перехода.|  
  
## <a name="remarks"></a>Примечания  
 Между указанными минимальным и максимальным значениями на протяжении всего переход в диапазоне синусоиды колеблется значение переменной анимации. Наклон параметр используется для устранения неоднозначности между двух возможных синусоидальных волн, указанных другими параметрами. Поскольку автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока затем возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="a-namecreatea--csinusoidaltransitionfromrangecreate"></a><a name="create"></a>CSinusoidalTransitionFromRange::Create  
 Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Параметры  
 `pLibrary`  
 Указатель на переход библиотеки, которая отвечает за создание стандартной переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход создано успешно; в противном случае — значение FALSE.  
  
##  <a name="a-namecsinusoidaltransitionfromrangea--csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a>CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange  
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
 Длительность перехода.  
  
 `dblMinimumValue`  
 Значение переменной анимации с помощью синусоиды wave.  
  
 `dblMaximumValue`  
 Значение переменной анимации пик синусоиды wave.  
  
 `period`  
 Период колебаний из синусоиды wave в секундах.  
  
 `slope`  
 Наклон в начале перехода.  
  
##  <a name="a-namemdblmaximumvaluea--csinusoidaltransitionfromrangemdblmaximumvalue"></a><a name="m_dblmaximumvalue"></a>CSinusoidalTransitionFromRange::m_dblMaximumValue  
 Значение переменной анимации пик синусоиды wave.  
  
```  
DOUBLE m_dblMaximumValue;  
```  
  
##  <a name="a-namemdblminimumvaluea--csinusoidaltransitionfromrangemdblminimumvalue"></a><a name="m_dblminimumvalue"></a>CSinusoidalTransitionFromRange::m_dblMinimumValue  
 Значение переменной анимации с помощью синусоиды wave.  
  
```  
DOUBLE m_dblMinimumValue;  
```  
  
##  <a name="a-namemdurationa--csinusoidaltransitionfromrangemduration"></a><a name="m_duration"></a>CSinusoidalTransitionFromRange::m_duration  
 Длительность перехода.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="a-namemperioda--csinusoidaltransitionfromrangemperiod"></a><a name="m_period"></a>CSinusoidalTransitionFromRange::m_period  
 Период колебаний из синусоиды wave в секундах.  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
##  <a name="a-namemslopea--csinusoidaltransitionfromrangemslope"></a><a name="m_slope"></a>CSinusoidalTransitionFromRange::m_slope  
 Наклон в начале перехода.  
  
```  
UI_ANIMATION_SLOPE m_slope;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

