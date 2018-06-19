---
title: Класс CCustomTransition | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89c3ec260fad8b0e2f8224c639aa745a9101e8b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358045"
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
|[CCustomTransition::Create](#create)|Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM. (Переопределяет [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|  
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Задает начальное значение будет применяться к переменной анимации, связанные с этот переход.|  
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Задает начальную скорость, которой будет применяться к переменной анимации, связанные с этот переход.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|Указывает, задан ли параметр начального значения с SetInitialValue.|  
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|Указывает, задан ли параметр с SetInitialVelocity начальной скоростью.|  
|[CCustomTransition::m_initialValue](#m_initialvalue)|Хранит начальное значение.|  
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|Хранит начальной скоростью.|  
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|Содержит указатель на пользовательские интерполятор.|  
  
## <a name="remarks"></a>Примечания  
 Класс CCustomTransitions позволяет разработчикам применять настраиваемые переходов. Его создание, используется в качестве стандартной перехода, но его конструктор принимает в качестве параметра указатель на пользовательские интерполятор. Выполните следующие действия для использования пользовательских переходов: 1. Создайте класс, производный от CCustomInterpolator и реализуйте по крайней мере InterpolateValue метод. 2. Убедитесь, что время существования объекта пользовательского интерполятора должно быть длиннее продолжительность анимации использования. 3. Создание экземпляра (с помощью оператора new) объекта CCustomTransition и передать указатель на пользовательские интерполятора в конструкторе. 4. Вызовите CCustomTransition::SetInitialValue и CCustomTransition::SetInitialVelocity, если эти параметры являются обязательными для пользовательских интерполяции. 5. Передайте указатель пользовательский переход метод AddTransition объекта анимации, значение которого необходимо анимировать с помощью пользовательского алгоритма. 6. Когда следует изменить значение объекта анимации API анимации Windows вызывает InterpolateValue (и другие необходимые методы) в CCustomInterpolator.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CCustomTransition`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="ccustomtransition"></a>  CCustomTransition::CCustomTransition  
 Создает объект пользовательский переход.  
  
```  
CCustomTransition(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>Параметры  
 `pInterpolator`  
 Указатель на пользовательские интерполятор.  
  
##  <a name="create"></a>  CCustomTransition::Create  
 Вызывает переход библиотеки для создания объекта инкапсулированный перехода COM.  
  
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
 Этот метод также можно задать начальное значение и Начальная скорость для применения к переменной анимации, связанный с этот переход. Для этого необходимо вызвать SetInitialValue и SetInitialVelocity, прежде чем платформа создает инкапсулированный перехода COM-объекта (это происходит при вызове CAnimationController::AnimateGroup).  
  
##  <a name="m_binitialvaluespecified"></a>  CCustomTransition::m_bInitialValueSpecified  
 Указывает, задан ли параметр начального значения с SetInitialValue.  
  
```  
BOOL m_bInitialValueSpecified;  
```  
  
##  <a name="m_binitialvelocityspecified"></a>  CCustomTransition::m_bInitialVelocitySpecified  
 Указывает, задан ли параметр с SetInitialVelocity начальной скоростью.  
  
```  
BOOL m_bInitialVelocitySpecified;  
```  
  
##  <a name="m_initialvalue"></a>  CCustomTransition::m_initialValue  
 Хранит начальное значение.  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="m_initialvelocity"></a>  CCustomTransition::m_initialVelocity  
 Хранит начальной скоростью.  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="m_pinterpolator"></a>  CCustomTransition::m_pInterpolator  
 Содержит указатель на пользовательские интерполятор.  
  
```  
CCustomInterpolator* m_pInterpolator;  
```  
  
##  <a name="setinitialvalue"></a>  CCustomTransition::SetInitialValue  
 Задает начальное значение будет применяться к переменной анимации, связанные с этот переход.  
  
```  
void SetInitialValue(DOUBLE initialValue);
```  
  
### <a name="parameters"></a>Параметры  
 `initialValue`  
  
##  <a name="setinitialvelocity"></a>  CCustomTransition::SetInitialVelocity  
 Задает начальную скорость, которой будет применяться к переменной анимации, связанные с этот переход.  
  
```  
void SetInitialVelocity(DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Параметры  
 `initialVelocity`  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
