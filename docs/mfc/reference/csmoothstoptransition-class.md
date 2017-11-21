---
title: "Класс CSmoothStopTransition | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
dev_langs: C++
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eaaa1ba7058047f8ce5c570be7ef68d64b0a5c15
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="csmoothstoptransition-class"></a>Класс CSmoothStopTransition
Инкапсулирует переход с плавной остановкой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CSmoothStopTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSmoothStopTransition::CSmoothStopTransition](#csmoothstoptransition)|Переход с плавной остановкой создает и инициализирует его максимальной продолжительности и конечное значение.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSmoothStopTransition::Create](#create)|Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSmoothStopTransition::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|  
|[CSmoothStopTransition::m_maximumDuration](#m_maximumduration)|Максимальная длительность перехода.|  
  
## <a name="remarks"></a>Примечания  
 Переход с плавной остановкой замедляет достигает заданного конечного значения, и достигается с скорости равно нулю. Продолжительность перехода определяется начальной скоростью разницу между начальное и конечное значения, а указанный максимальный период времени. Если ни одно решение, состоящий из одного параболическим дуги, этот метод создает кубический переход. Так как автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока, то возвращается значение NULL. Изменение переменных-членов, после создания этот объект COM не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="create"></a>CSmoothStopTransition::Create  
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
  
##  <a name="csmoothstoptransition"></a>CSmoothStopTransition::CSmoothStopTransition  
 Переход с плавной остановкой создает и инициализирует его максимальной продолжительности и конечное значение.  
  
```  
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,  
    DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>Параметры  
 `maximumDuration`  
 Максимальная длительность перехода.  
  
 `dblFinalValue`  
 Значение переменной анимации в конце перехода.  
  
##  <a name="m_dblfinalvalue"></a>CSmoothStopTransition::m_dblFinalValue  
 Значение переменной анимации в конце перехода.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_maximumduration"></a>CSmoothStopTransition::m_maximumDuration  
 Максимальная длительность перехода.  
  
```  
UI_ANIMATION_SECONDS m_maximumDuration;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
