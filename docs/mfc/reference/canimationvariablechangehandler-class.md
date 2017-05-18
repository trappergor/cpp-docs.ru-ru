---
title: "Класс CAnimationVariableChangeHandler | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariableChangeHandler class
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 46c4eb9210b69c527375b12100ab7cc22fef0176
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="canimationvariablechangehandler-class"></a>Класс CAnimationVariableChangeHandler
Реализует обратный вызов, используемый API анимации при изменении значения переменной анимации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Создает объект `CAnimationVariableChangeHandler`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CreateInstance`|Создает экземпляр `CAnimationVariableChangeHandler` объекта.|  
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|Вызывается при изменении значения переменной анимации. (Переопределяет `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.)|  
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|Хранит указатель на контроллер анимации для события маршрута.|  
  
## <a name="remarks"></a>Примечания  
 Этот обработчик событий создается и передается `IUIAnimationVariable::SetVariableChangeHandler` при вызове метода `CAnimationVariable::EnableValueChangedEvent` или `CAnimationBaseObject::EnableValueChangedEvent` (позволяет это событие для всех переменных анимации, инкапсулированный в объекте анимации).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="onvaluechanged"></a>CAnimationVariableChangeHandler::OnValueChanged  
 Вызывается при изменении значения переменной анимации.  
  
```  
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```  
  
### <a name="parameters"></a>Параметры  
 `storyboard`  
 Раскадровки, который выполняет анимацию переменной.  
  
 `variable`  
 Переменная анимации, которая была обновлена.  
  
 `newValue`  
 Новое значение.  
  
 `previousValue`  
 Предыдущее значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается значение S_OK. В противном случае — возвращает код ошибки HRESULT.  
  
##  <a name="setanimationcontroller"></a>CAnimationVariableChangeHandler::SetAnimationController  
 Хранит указатель на контроллер анимации для события маршрута.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Параметры  
 `pAnimationController`  
 Указатель на контроллер анимации, который будет получать события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

