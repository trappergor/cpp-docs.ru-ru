---
title: Класс CFirePropNotifyEvent | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 728f4e973a7ef74dcdbb44150375df235e0d990e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cfirepropnotifyevent-class"></a>Класс CFirePropNotifyEvent
Этот класс предоставляет методы для уведомления контейнера приемник об изменениях свойств элемента управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Статический) Уведомляет контейнера приемник измененного свойства элемента управления.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Статический) Уведомляет приемника контейнера, который будет изменено свойство элемента управления.|  
  
## <a name="remarks"></a>Примечания  
 `CFirePropNotifyEvent` есть два способа уведомления стока контейнера, свойство элемента управления был изменен или изменением.  
  
 Если класс, реализующий элемент управления является производным от `IPropertyNotifySink`, `CFirePropNotifyEvent` методы вызываются при вызове `FireOnRequestEdit` или `FireOnChanged`. Если ваш класс элемента управления не является производным от `IPropertyNotifySink`, вызовы этих функций возвращает `S_OK`.  
  
 Дополнительные сведения о создании элементов управления см. в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged  
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
  
##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit  
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
