---
title: Класс Ипропертинотифисинккп
ms.date: 11/04/2016
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
ms.openlocfilehash: 9838a48b078cbc59a5ae86669ad9f26792d9816e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495626"
---
# <a name="ipropertynotifysinkcp-class"></a>Класс Ипропертинотифисинккп

Этот класс предоставляет интерфейс [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) в качестве исходящего интерфейса для подключаемого объекта.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IPropertyNotifySinkCP`.

*КДВ*<br/>
Класс, управляющий соединениями между точкой подключения и ее приемниками. Значение по умолчанию — [ккомдинамикункаррай](../../atl/reference/ccomdynamicunkarray-class.md), что позволяет устанавливать неограниченное число подключений. Можно также использовать [ккомункаррай](../../atl/reference/ccomunkarray-class.md), который указывает фиксированное число соединений.

## <a name="remarks"></a>Примечания

`IPropertyNotifySinkCP`наследует все методы через его базовый класс [иконнектионпоинтимпл](../../atl/reference/iconnectionpointimpl-class.md).

Интерфейс [ипропертинотифисинк](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) позволяет объекту-приемнику получать уведомления об изменениях свойств. Класс `IPropertyNotifySinkCP` предоставляет этот интерфейс в качестве исходящего интерфейса для подключаемого объекта. Клиент должен реализовать `IPropertyNotifySink` методы в приемнике.

Создайте класс, производный `IPropertyNotifySinkCP` от класса, если нужно создать точку подключения, `IPropertyNotifySink` представляющую интерфейс.

Дополнительные сведения об использовании точек подключения в ATL см. в статье [точки подключения](../../atl/atl-connection-points.md).

## <a name="requirements"></a>Требования

**Заголовок:** атлктл. h

## <a name="see-also"></a>См. также

[Класс IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[Класс IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
