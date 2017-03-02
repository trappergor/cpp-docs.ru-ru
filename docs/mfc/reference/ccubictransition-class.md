---
title: "Класс CCubicTransition | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCubicTransition
- afxanimationcontroller/CCubicTransition
dev_langs:
- C++
helpviewer_keywords:
- CCubicTransition class
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
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
ms.openlocfilehash: 511dc175d51db7887a462aaf63f4f91290375751
ms.lasthandoff: 02/24/2017

---
# <a name="ccubictransition-class"></a>Класс CCubicTransition
Инкапсулирует кубический переход.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCubicTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCubicTransition::CCubicTransition](#ccubictransition)|Создает объект перехода и инициализирует его параметры.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCubicTransition::Create](#create)|Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCubicTransition::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|  
|[CCubicTransition::m_dblFinalVelocity](#m_dblfinalvelocity)|Скорость переменной в конце перехода.|  
|[CCubicTransition::m_duration](#m_duration)|Длительность перехода.|  
  
## <a name="remarks"></a>Примечания  
 При кубический переход значение переменной анимации изменяют исходное значение в указанный последнее значение на протяжении перехода заканчивается на указанной скорости. Поскольку автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока затем возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CCubicTransition`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="a-nameccubictransitiona--ccubictransitionccubictransition"></a><a name="ccubictransition"></a>CCubicTransition::CCubicTransition  
 Создает объект перехода и инициализирует его параметры.  
  
```  
CCubicTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue,  
    DOUBLE finalVelocity);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Длительность перехода.  
  
 `finalValue`  
 Значение переменной анимации в конце перехода.  
  
 `finalVelocity`  
 Скорость переменной в конце перехода.  
  
##  <a name="a-namecreatea--ccubictransitioncreate"></a><a name="create"></a>CCubicTransition::Create  
 Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Параметры  
`pLibrary`  
 Указатель на [IUIAnimationTransitionLibrary интерфейс](https://msdn.microsoft.com/library/windows/desktop/dd371897), определяющего библиотеки стандартных переходов.  

### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход создано успешно; в противном случае — значение FALSE.  
  
##  <a name="a-namemdblfinalvaluea--ccubictransitionmdblfinalvalue"></a><a name="m_dblfinalvalue"></a>CCubicTransition::m_dblFinalValue  
 Значение переменной анимации в конце перехода.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="a-namemdblfinalvelocitya--ccubictransitionmdblfinalvelocity"></a><a name="m_dblfinalvelocity"></a>CCubicTransition::m_dblFinalVelocity  
 Скорость переменной в конце перехода.  
  
```  
DOUBLE m_dblFinalVelocity;  
```  
  
##  <a name="a-namemdurationa--ccubictransitionmduration"></a><a name="m_duration"></a>CCubicTransition::m_duration  
 Длительность перехода.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

