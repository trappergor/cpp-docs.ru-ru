---
title: Класс CAtlAutoThreadModule
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: acd277160bc277e919a2802541310aa55446e00c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619717"
---
# <a name="catlautothreadmodule-class"></a>Класс CAtlAutoThreadModule

Этот класс реализует COM-сервера пула потоков, модель с подразделением.

> [!IMPORTANT]
> Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>Примечания

`CAtlAutoThreadModule` является производным от [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) и реализует COM-сервера пула потоков, модель с подразделением. `CAtlAutoThreadModule` использует [CComApartment](../../atl/reference/ccomapartment-class.md) для управления как подразделение, для каждого потока в модуле.

Необходимо использовать [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) макроса в определении класса объекта, чтобы указать [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрика класса. Затем следует добавить один экземпляр класса, производного от `CAtlAutoThreadModuleT` например `CAtlAutoThreadModule`. Пример:

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> Этот класс заменяет устаревшее [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlAutoThreadModule`

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="see-also"></a>См. также

[Класс CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)<br/>
[Класс IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Модульные классы](../../atl/atl-module-classes.md)
