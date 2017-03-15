---
title: "Класс CDiscreteTransition | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDiscreteTransition
- afxanimationcontroller/CDiscreteTransition
dev_langs:
- C++
helpviewer_keywords:
- CDiscreteTransition class
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: dcec642fede0ec6895c928925676232319099be7
ms.lasthandoff: 02/24/2017

---
# <a name="cdiscretetransition-class"></a>Класс CDiscreteTransition
Инкапсулирует отдельный переход.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDiscreteTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDiscreteTransition::CDiscreteTransition](#cdiscretetransition)|Создает объект отдельный переход и инициализирует его параметры.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDiscreteTransition::Create](#create)|Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDiscreteTransition::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|  
|[CDiscreteTransition::m_delay](#m_delay)|Количество времени, на который мгновенно переключиться на окончательное значение задержки.|  
|[CDiscreteTransition::m_hold](#m_hold)|Количество времени, в котором для хранения переменной в свое последнее значение.|  
  
## <a name="remarks"></a>Примечания  
 Во время отдельный переход переменной анимации остается в начальное значение для времени, а затем переключается мгновенно указанного окончательное значение и сохраняет это значение для времени данного удержания. Поскольку автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока затем возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="a-namecdiscretetransitiona--cdiscretetransitioncdiscretetransition"></a><a name="cdiscretetransition"></a>CDiscreteTransition::CDiscreteTransition  
 Создает объект отдельный переход и инициализирует его параметры.  
  
```  
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,  
    DOUBLE dblFinalValue,  
    UI_ANIMATION_SECONDS hold);
```  
  
### <a name="parameters"></a>Параметры  
 `delay`  
 Количество времени, на который мгновенно переключиться на окончательное значение задержки.  
  
 `dblFinalValue`  
 Значение переменной анимации в конце перехода.  
  
 `hold`  
 Количество времени, в котором для хранения переменной в свое последнее значение.  
  
##  <a name="a-namecreatea--cdiscretetransitioncreate"></a><a name="create"></a>CDiscreteTransition::Create  
 Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
`pLibrary`  
 Указатель на [IUIAnimationTransitionLibrary интерфейс](https://msdn.microsoft.com/library/windows/desktop/dd371897), определяющего библиотеки стандартных переходов.  

  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход создано успешно; в противном случае — значение FALSE.  
  
##  <a name="a-namemdblfinalvaluea--cdiscretetransitionmdblfinalvalue"></a><a name="m_dblfinalvalue"></a>CDiscreteTransition::m_dblFinalValue  
 Значение переменной анимации в конце перехода.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="a-namemdelaya--cdiscretetransitionmdelay"></a><a name="m_delay"></a>CDiscreteTransition::m_delay  
 Количество времени, на который мгновенно переключиться на окончательное значение задержки.  
  
```  
UI_ANIMATION_SECONDS m_delay;  
```  
  
##  <a name="a-namemholda--cdiscretetransitionmhold"></a><a name="m_hold"></a>CDiscreteTransition::m_hold  
 Количество времени, в котором для хранения переменной в свое последнее значение.  
  
```  
UI_ANIMATION_SECONDS m_hold;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

