---
title: Класс IPropertyNotifySinkCP | Документация Майкрософт
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
ms.openlocfilehash: 66fd7b267a70b962bb5c28bb5835bd96d44a92f0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879193"
---
# <a name="ipropertynotifysinkcp-class"></a>Класс IPropertyNotifySinkCP
Этот класс предоставляет [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейс как исходящий интерфейс в подключаемом объекте.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IPropertyNotifySinkCP`.  
  
 *CDV*  
 Класс, который управляет подключениями между точкой подключения и его приемников. Значение по умолчанию — [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), что позволяет неограниченное количество подключений. Можно также использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), который задает фиксированное количество подключений.  
  
## <a name="remarks"></a>Примечания  
 `IPropertyNotifySinkCP` наследует все методы с помощью базового класса, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейс позволяет объекту приемник для получения уведомлений об изменениях свойств. Класс `IPropertyNotifySinkCP` предоставляет этот интерфейс как исходящий интерфейс в подключаемом объекте. Клиент должен реализовывать `IPropertyNotifySink` методы в приемнике.  
  
 Наследование класса из `IPropertyNotifySinkCP` Если вы хотите создать точку подключения, представляющий `IPropertyNotifySink` интерфейс.  
  
 Дополнительные сведения об использовании точки подключения библиотеки ATL, см. в статье [точек подключения](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
## <a name="see-also"></a>См. также  
 [Класс IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)   
 [Класс IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
