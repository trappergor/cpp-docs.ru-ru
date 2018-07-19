---
title: Класс CConstantTransition | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::Create
- AFXANIMATIONCONTROLLER/CConstantTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CConstantTransition [MFC], CConstantTransition
- CConstantTransition [MFC], Create
- CConstantTransition [MFC], m_duration
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48a8ccb49001b93ded52edc732fc59222775e6f8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954031"
---
# <a name="cconstanttransition-class"></a>Класс CConstantTransition
Инкапсулирует постоянный переход.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CConstantTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CConstantTransition::CConstantTransition](#cconstanttransition)|Создает объект перехода и инициализирует его длительности.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CConstantTransition::Create](#create)|Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CConstantTransition::m_duration](#m_duration)|Продолжительность перехода.|  
  
## <a name="remarks"></a>Примечания  
 Во время перехода константой значение переменной анимации остается в исходное значение на протяжении перехода. Так как автоматически очищаются все переходы, рекомендуется выделить их с помощью оператора new. Инкапсулированный объект IUIAnimationTransition COM созданный CAnimationController::AnimateGroup, пока, то возвращается значение NULL. Изменение переменных-членов, после создания этот объект COM не оказывает влияния.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CConstantTransition`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="cconstanttransition"></a>  CConstantTransition::CConstantTransition  
 Создает объект перехода и инициализирует его длительности.  
  
```  
CConstantTransition (UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Параметры  
 *Длительность*  
 Продолжительность перехода.  
  
##  <a name="create"></a>  CConstantTransition::Create  
 Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Параметры  
 *pLibrary*  
 Указатель на [IUIAnimationTransitionLibrary интерфейс](https://msdn.microsoft.com/library/windows/desktop/dd371897), который определяет библиотеку стандартных переходов.  

### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если переход создан успешно; в противном случае — значение FALSE.  
  
##  <a name="m_duration"></a>  CConstantTransition::m_duration  
 Продолжительность перехода.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
