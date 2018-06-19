---
title: Класс IPropertyNotifySinkCP | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9612cf65479e474b9a6e89a8f5a57ca078c9ed0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361630"
---
# <a name="ipropertynotifysinkcp-class"></a>Класс IPropertyNotifySinkCP
Этот класс предоставляет [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейс в качестве исходящего интерфейса доступный для соединения объект.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IPropertyNotifySinkCP`.  
  
 `CDV`  
 Класс, который управляет соединениями между точкой подключения и его журналах. Значение по умолчанию — [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), что позволяет неограниченное число подключений. Можно также использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), который задает фиксированное число подключений.  
  
## <a name="remarks"></a>Примечания  
 `IPropertyNotifySinkCP` наследует все методы через его базовый класс [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейс позволяет объекту приемника для получения уведомлений об изменениях свойств. Класс `IPropertyNotifySinkCP` предоставляет этот интерфейс в виде исходящего интерфейса доступный для соединения объект. Клиент должен реализовывать `IPropertyNotifySink` методы приемника.  
  
 Создайте производный класс от `IPropertyNotifySinkCP` при необходимости создать точку подключения, представляющий `IPropertyNotifySink` интерфейса.  
  
 Дополнительные сведения об использовании точек соединения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
## <a name="see-also"></a>См. также  
 [Класс IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)   
 [Класс IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
