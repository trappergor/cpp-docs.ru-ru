---
title: Класс IPropertyNotifySinkCP
ms.date: 11/04/2016
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
ms.openlocfilehash: b96e5345923d04de74dace173a80b8c4d3ee917f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280593"
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

*T*<br/>
Ваш класс, производный от `IPropertyNotifySinkCP`.

*CDV*<br/>
Класс, который управляет подключениями между точкой подключения и его приемников. Значение по умолчанию — [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), что позволяет неограниченное количество подключений. Можно также использовать [CComUnkArray](../../atl/reference/ccomunkarray-class.md), который задает фиксированное количество подключений.

## <a name="remarks"></a>Примечания

`IPropertyNotifySinkCP` наследует все методы с помощью базового класса, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).

[IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) интерфейс позволяет объекту приемник для получения уведомлений об изменениях свойств. Класс `IPropertyNotifySinkCP` предоставляет этот интерфейс как исходящий интерфейс в подключаемом объекте. Клиент должен реализовывать `IPropertyNotifySink` методы в приемнике.

Наследование класса из `IPropertyNotifySinkCP` Если вы хотите создать точку подключения, представляющий `IPropertyNotifySink` интерфейс.

Дополнительные сведения об использовании точки подключения библиотеки ATL, см. в статье [точек подключения](../../atl/atl-connection-points.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

## <a name="see-also"></a>См. также

[Класс IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[Класс IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
