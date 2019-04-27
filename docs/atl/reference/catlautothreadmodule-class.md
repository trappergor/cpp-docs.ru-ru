---
title: Класс CAtlAutoThreadModule
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: 1ec66bf77d8dd705cb2e1e93f70a885ab96420a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247301"
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
