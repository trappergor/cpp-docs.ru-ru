---
title: "Класс CReversalTransition | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CReversalTransition
- CReversalTransition
dev_langs:
- C++
helpviewer_keywords:
- CReversalTransition class
ms.assetid: e89516be-2d07-4885-95a8-fc278f46e3ad
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
ms.openlocfilehash: 028ea275cc345513248e76dcf5b0eba931823b7a
ms.lasthandoff: 02/24/2017

---
# <a name="creversaltransition-class"></a>Класс CReversalTransition
Инкапсулирует обратный переход.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CReversalTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CReversalTransition::CReversalTransition](#creversaltransition)|Создает объект обратный переход и инициализирует его продолжительность.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CReversalTransition::Create](#create)|Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CReversalTransition::m_duration](#m_duration)|Длительность перехода.|  
  
## <a name="remarks"></a>Примечания  
 Обратный переход плавно меняет направление за заданный период. Окончательное значение будет таким же, как начальное значение и Конечная скорость будет отрицательной Начальная скорость. Поскольку автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока затем возвращается значение NULL. Изменение переменных-членов, после создания COM-объекта не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CReversalTransition](../../mfc/reference/creversaltransition-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="a-namecreatea--creversaltransitioncreate"></a><a name="create"></a>CReversalTransition::Create  
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
  
##  <a name="a-namecreversaltransitiona--creversaltransitioncreversaltransition"></a><a name="creversaltransition"></a>CReversalTransition::CReversalTransition  
 Создает объект обратный переход и инициализирует его продолжительность.  
  
```  
CReversalTransition(UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Параметры  
 `duration`  
 Длительность перехода.  
  
##  <a name="a-namemdurationa--creversaltransitionmduration"></a><a name="m_duration"></a>CReversalTransition::m_duration  
 Длительность перехода.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

