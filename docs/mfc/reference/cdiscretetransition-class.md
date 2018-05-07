---
title: Класс CDiscreteTransition | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::Create
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_delay
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_hold
dev_langs:
- C++
helpviewer_keywords:
- CDiscreteTransition [MFC], CDiscreteTransition
- CDiscreteTransition [MFC], Create
- CDiscreteTransition [MFC], m_dblFinalValue
- CDiscreteTransition [MFC], m_delay
- CDiscreteTransition [MFC], m_hold
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 858304a41cb015711393ea6cc41e73ddbcc8cd8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdiscretetransition-class"></a>Класс CDiscreteTransition
Инкапсулирует отдельный переход.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDiscreteTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDiscreteTransition::CDiscreteTransition](#cdiscretetransition)|Создает объект отдельный переход и инициализирует его параметры.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDiscreteTransition::Create](#create)|Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDiscreteTransition::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|  
|[CDiscreteTransition::m_delay](#m_delay)|Количество времени, на которое задержать мгновенный переход в последнее значение.|  
|[CDiscreteTransition::m_hold](#m_hold)|Количество времени, на который для хранения переменной в свое последнее значение.|  
  
## <a name="remarks"></a>Примечания  
 Во время отдельный переход переменной анимации остается в начальное значение для времени заданной задержки, а затем переключается мгновенно указанного конечного значения и сохраняет это значение для времени ожидания, заданного. Так как автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока, то возвращается значение NULL. Изменение переменных-членов, после создания этот объект COM не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="cdiscretetransition"></a>  CDiscreteTransition::CDiscreteTransition  
 Создает объект отдельный переход и инициализирует его параметры.  
  
```  
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,  
    DOUBLE dblFinalValue,  
    UI_ANIMATION_SECONDS hold);
```  
  
### <a name="parameters"></a>Параметры  
 `delay`  
 Количество времени, на которое задержать мгновенный переход в последнее значение.  
  
 `dblFinalValue`  
 Значение переменной анимации в конце перехода.  
  
 `hold`  
 Количество времени, на который для хранения переменной в свое последнее значение.  
  
##  <a name="create"></a>  CDiscreteTransition::Create  
 Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
`pLibrary`  
 Указатель на [IUIAnimationTransitionLibrary интерфейс](https://msdn.microsoft.com/library/windows/desktop/dd371897), который определяет библиотеку стандартных переходов.  

  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.  
  
##  <a name="m_dblfinalvalue"></a>  CDiscreteTransition::m_dblFinalValue  
 Значение переменной анимации в конце перехода.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_delay"></a>  CDiscreteTransition::m_delay  
 Количество времени, на которое задержать мгновенный переход в последнее значение.  
  
```  
UI_ANIMATION_SECONDS m_delay;  
```  
  
##  <a name="m_hold"></a>  CDiscreteTransition::m_hold  
 Количество времени, на который для хранения переменной в свое последнее значение.  
  
```  
UI_ANIMATION_SECONDS m_hold;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
