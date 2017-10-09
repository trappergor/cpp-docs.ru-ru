---
title: "Класс CFirePropNotifyEvent | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
dev_langs:
- C++
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 1fb22263b877aaff3e30e56efff2a005bc024f2e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="cfirepropnotifyevent-class"></a>Класс CFirePropNotifyEvent
Этот класс предоставляет методы для уведомления контейнера приемник об изменениях свойств элемента управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Статический) Уведомляет контейнера приемник измененного свойства элемента управления.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Статический) Уведомляет приемника контейнера, который будет изменено свойство элемента управления.|  
  
## <a name="remarks"></a>Примечания  
 `CFirePropNotifyEvent`есть два способа уведомления стока контейнера, свойство элемента управления был изменен или изменением.  
  
 Если класс, реализующий элемент управления является производным от `IPropertyNotifySink`, `CFirePropNotifyEvent` методы вызываются при вызове `FireOnRequestEdit` или `FireOnChanged`. Если ваш класс элемента управления не является производным от `IPropertyNotifySink`, вызовы этих функций возвращает `S_OK`.  
  
 Дополнительные сведения о создании элементов управления см. в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="fireonchanged"></a>CFirePropNotifyEvent::FireOnChanged  
 Уведомляет все подключения [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейсы (на все точки подключения объекта), которые изменилось значение свойства указанного объекта.  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на **IUnknown** объекта, отправляющего уведомление.  
  
 *dispID*  
 [in] Идентификатор измененного свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно вызвать, даже если элемент управления не поддерживает точки подключения.  
  
##  <a name="fireonrequestedit"></a>CFirePropNotifyEvent::FireOnRequestEdit  
 Уведомляет все подключения [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейсы (на все точки подключения объекта), свойство указанного объекта будет изменена.  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на **IUnknown** объекта, отправляющего уведомление.  
  
 *dispID*  
 [in] Идентификатор свойства будет изменен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно вызвать, даже если элемент управления не поддерживает точки подключения.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

