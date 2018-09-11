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
ms.openlocfilehash: ab7e3731132e1b9ed9381a7b97347406b620df70
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759669"
---
# <a name="ipropertynotifysinkcp-class"></a>Класс IPropertyNotifySinkCP

Этот класс предоставляет [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) интерфейс как исходящий интерфейс в подключаемом объекте.

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

[IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) интерфейс позволяет объекту приемник для получения уведомлений об изменениях свойств. Класс `IPropertyNotifySinkCP` предоставляет этот интерфейс как исходящий интерфейс в подключаемом объекте. Клиент должен реализовывать `IPropertyNotifySink` методы в приемнике.

Наследование класса из `IPropertyNotifySinkCP` Если вы хотите создать точку подключения, представляющий `IPropertyNotifySink` интерфейс.

Дополнительные сведения об использовании точки подключения библиотеки ATL, см. в статье [точек подключения](../../atl/atl-connection-points.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="see-also"></a>См. также

[Класс IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)   
[Класс IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
