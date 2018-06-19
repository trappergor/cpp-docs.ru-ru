---
title: Класс CAnimationVariableChangeHandler | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e35fc33b26fa6bead73458a46d7c4edee1cf136
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350996"
---
# <a name="canimationvariablechangehandler-class"></a>Класс CAnimationVariableChangeHandler
Реализует обратный вызов, используемый API анимации при изменении значения переменной анимации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Создает объект `CAnimationVariableChangeHandler`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CAnimationVariableChangeHandler::CreateInstance`|Создает экземпляр `CAnimationVariableChangeHandler` объекта.|  
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|Вызывается при изменении значения переменной анимации. (Переопределяет `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.)|  
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|Содержит указатель на контроллер анимации на маршруте события.|  
  
## <a name="remarks"></a>Примечания  
 Этот обработчик событий создается и передается `IUIAnimationVariable::SetVariableChangeHandler` при вызове метод `CAnimationVariable::EnableValueChangedEvent` или `CAnimationBaseObject::EnableValueChangedEvent` (разрешает это событие для всех переменных анимации, содержащийся в объекте анимации).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxanimationcontroller.h  
  
##  <a name="onvaluechanged"></a>  CAnimationVariableChangeHandler::OnValueChanged  
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
 Раскадровка, анимации переменной.  
  
 `variable`  
 Переменной анимации, которая была обновлена.  
  
 `newValue`  
 Новое значение.  
  
 `previousValue`  
 Предыдущее значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод выполнен успешно, возвращается значение S_OK. В противном случае возвращается код ошибки HRESULT.  
  
##  <a name="setanimationcontroller"></a>  CAnimationVariableChangeHandler::SetAnimationController  
 Содержит указатель на контроллер анимации на маршруте события.  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>Параметры  
 `pAnimationController`  
 Указатель на контроллер анимации, который будет получать события.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
