---
title: "Класс IPropertyNotifySinkCP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 21
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: feff2467d6d72e9d0a9186dc269f48eb26cbfee2
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="ipropertynotifysinkcp-class"></a>Класс IPropertyNotifySinkCP
Этот класс предоставляет [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейс в качестве исходящего интерфейса доступный для соединения объект.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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
 Класс, который управляет соединениями между точкой подключения и его приемники. Значение по умолчанию — [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), который позволяет неограниченное число подключений. Можно также использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), который указывает ограниченное число подключений.  
  
## <a name="remarks"></a>Примечания  
 `IPropertyNotifySinkCP`наследует все методы через его базового класса, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) интерфейс позволяет объекту приемника для получения уведомлений об изменениях свойств. Класс `IPropertyNotifySinkCP` предоставляет этот интерфейс как исходящий интерфейс на доступный для соединения объект. Клиент должен реализовывать `IPropertyNotifySink` методы приемника.  
  
 Создайте производный класс от `IPropertyNotifySinkCP` , если требуется создать точку подключения, которая представляет `IPropertyNotifySink` интерфейса.  
  
 Дополнительные сведения об использовании точек соединения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
## <a name="see-also"></a>См. также  
 [Класс IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)   
 [Класс IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

