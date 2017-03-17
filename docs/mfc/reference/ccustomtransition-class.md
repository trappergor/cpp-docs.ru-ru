---
title: "Класс CCustomTransition | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
dev_langs:
- C++
helpviewer_keywords:
- CCustomTransition class
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 483fb2ab84d2c41fe4666a4ea333c0be8b07caee
ms.lasthandoff: 02/24/2017

---
# <a name="ccustomtransition-class"></a>Класс CCustomTransition
Реализует пользовательский переход.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CCustomTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCustomTransition::CCustomTransition](#ccustomtransition)|Создает объект пользовательский переход.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCustomTransition::Create](#create)|Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Задает начальное значение будет применяться к переменной анимации, связанные с этого перехода.|  
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Задает начальную скорость, которой будет назначен переменной анимации, связанные с этого перехода.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|Указывает, задан ли параметр начального значения с SetInitialValue.|  
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|Указывает, задан ли Начальная скорость с SetInitialVelocity.|  
|[CCustomTransition::m_initialValue](#m_initialvalue)|Хранит начальное значение.|  
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|Хранит начальной скоростью.|  
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|Хранит указатель на пользовательские интерполятор.|  
  
## <a name="remarks"></a>Примечания  
 Класс CCustomTransitions позволяет разработчикам реализовывать пользовательские переходов. Он создал и использовать в качестве стандартных перехода, но его конструктор принимает в качестве параметра указатель на пользовательские интерполятор. Выполните следующие действия для использования пользовательских переходов: 1. Создайте класс, производный от CCustomInterpolator и по крайней мере реализовать метод InterpolateValue. 2. Убедитесь, что время существования объекта пользовательского интерполятора должно быть длиннее продолжительность анимации используется. 3. Создание экземпляра (с помощью оператора new) объекта CCustomTransition и передать указатель на пользовательские интерполятор в конструкторе. 4. Если эти параметры являются обязательными для пользовательской интерполяция, вызовите CCustomTransition::SetInitialValue и CCustomTransition::SetInitialVelocity. 5. Передайте указатель пользовательский переход к методу AddTransition объекта анимации, значение которого анимации с помощью пользовательского алгоритма. 6. Когда следует изменить значение объекта анимации Windows API анимации вызывает InterpolateValue (и другие необходимые методы) в CCustomInterpolator.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CCustomTransition`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="ccustomtransition"></a>CCustomTransition::CCustomTransition  
 Создает объект пользовательский переход.  
  
```  
CCustomTransition(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>Параметры  
 `pInterpolator`  
 Указатель на пользовательские интерполятор.  
  
##  <a name="create"></a>CCustomTransition::Create  
 Вызывает переход библиотеку для создания объекта инкапсулированный перехода COM.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,  
    IUIAnimationTransitionFactory* pFactory);
```  
  
### <a name="parameters"></a>Параметры  
 `pFactory`  
 Указатель на переход фабрики, который отвечает за создание пользовательских переходов.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Этот метод также можно задать начальное значение и Начальная скорость для применения к переменной анимации, связанный с этого перехода. Для этого необходимо вызвать SetInitialValue и SetInitialVelocity, прежде чем платформа создает инкапсулированный перехода COM-объект (это происходит при вызове CAnimationController::AnimateGroup).  
  
##  <a name="m_binitialvaluespecified"></a>CCustomTransition::m_bInitialValueSpecified  
 Указывает, задан ли параметр начального значения с SetInitialValue.  
  
```  
BOOL m_bInitialValueSpecified;  
```  
  
##  <a name="m_binitialvelocityspecified"></a>CCustomTransition::m_bInitialVelocitySpecified  
 Указывает, задан ли Начальная скорость с SetInitialVelocity.  
  
```  
BOOL m_bInitialVelocitySpecified;  
```  
  
##  <a name="m_initialvalue"></a>CCustomTransition::m_initialValue  
 Хранит начальное значение.  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="m_initialvelocity"></a>CCustomTransition::m_initialVelocity  
 Хранит начальной скоростью.  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="m_pinterpolator"></a>CCustomTransition::m_pInterpolator  
 Хранит указатель на пользовательские интерполятор.  
  
```  
CCustomInterpolator* m_pInterpolator;  
```  
  
##  <a name="setinitialvalue"></a>CCustomTransition::SetInitialValue  
 Задает начальное значение будет применяться к переменной анимации, связанные с этого перехода.  
  
```  
void SetInitialValue(DOUBLE initialValue);
```  
  
### <a name="parameters"></a>Параметры  
 `initialValue`  
  
##  <a name="setinitialvelocity"></a>CCustomTransition::SetInitialVelocity  
 Задает начальную скорость, которой будет назначен переменной анимации, связанные с этого перехода.  
  
```  
void SetInitialVelocity(DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Параметры  
 `initialVelocity`  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

