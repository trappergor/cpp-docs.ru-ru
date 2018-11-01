---
title: Класс CComAutoDeleteCriticalSection
ms.date: 11/04/2016
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
ms.openlocfilehash: 93b9a266bba59b80a7661cf63046dcfe63f3edb2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431178"
---
# <a name="ccomautodeletecriticalsection-class"></a>Класс CComAutoDeleteCriticalSection

Этот класс предоставляет методы для получения и освобождения владения объект критической секции.

## <a name="syntax"></a>Синтаксис

```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```

## <a name="remarks"></a>Примечания

`CComAutoDeleteCriticalSection` является производным от класса [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Тем не менее `CComAutoDeleteCriticalSection` переопределяет [термин](ccomsafedeletecriticalsection-class.md#term) метод **частного** доступа, который обеспечивает внутреннюю память очистки, только когда экземпляры этого класса не выйдут из области или будут явно удалены из объем памяти.

Этот класс предоставляет дополнительные методы не через своего базового класса. См. в разделе [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) и [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) Дополнительные сведения о вспомогательных классов критический раздел.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)

`CComAutoDeleteCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

## <a name="see-also"></a>См. также

[Класс CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)<br/>
[Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
