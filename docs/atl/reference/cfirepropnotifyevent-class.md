---
title: Класс CFirePropNotifyEvent | Документация Майкрософт
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
ms.openlocfilehash: 3ec6fb0d54cd748b707c81b88e09fb7d846aaa2f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194428"
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
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Статический) Уведомляет приемника контейнера, измененного свойства элемента управления.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Статический) Уведомляет контейнера приемника, который собираетесь изменить свойства элемента управления.|  
  
## <a name="remarks"></a>Примечания  
 `CFirePropNotifyEvent` содержит два метода, уведомляющие приемника контейнера, который свойства элемента управления был изменен или изменением.  
  
 Если класс, реализующий элемент управления является производным от `IPropertyNotifySink`, `CFirePropNotifyEvent` методы вызываются при вызове `FireOnRequestEdit` или `FireOnChanged`. Если ваш класс элемента управления не является производным от `IPropertyNotifySink`, вызовы этих функций, верните значение s_ок.  
  
 Дополнительные сведения о создании элементов управления см. в разделе [учебник по ATL](../../atl/active-template-library-atl-tutorial.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged  
 Уведомляет все подключенные [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) интерфейсы (на все точки подключения объекта), свойство указанного объекта изменилось.  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на `IUnknown` объекта отправки уведомлений.  
  
 *dispID*  
 [in] Идентификатор измененного свойства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно вызывать, даже если элемент управления не поддерживает точки подключения.  
  
##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit  
 Уведомляет все подключенные [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) интерфейсы (на все точки подключения объекта), свойство указанного объекта будет изменена.  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Указатель на `IUnknown` объекта отправки уведомлений.  
  
 *dispID*  
 [in] Идентификатор свойства изменением.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Одно из стандартных значений HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно вызывать, даже если элемент управления не поддерживает точки подключения.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
