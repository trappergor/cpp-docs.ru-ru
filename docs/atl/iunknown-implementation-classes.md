---
title: Классы для реализации IUnknown (ATL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.Iunknown
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
ms.openlocfilehash: 97ca30c90cb8fa85685e30aa61d954008cf7cc54
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297571"
---
# <a name="iunknown-implementation-classes"></a>Классы для реализации IUnknown

Следующие классы реализуют `IUnknown` и связанными методами:

- [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) управляет подсчетом ссылок для статистическим и неагрегированные объектов. Позволяет указать потоковую модель.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) управляет подсчетом ссылок для статистическим и неагрегированные объектов. Использует потоковую модель сервера по умолчанию.

- [CComAggObject](../atl/reference/ccomaggobject-class.md) реализует `IUnknown` для объединенного объекта.

- [CComObject](../atl/reference/ccomobject-class.md) реализует `IUnknown` неагрегированные объекта.

- [CComPolyObject](../atl/reference/ccompolyobject-class.md) реализует `IUnknown` для статистически обработанные и неагрегированные объектов. С помощью `CComPolyObject` избавляет от необходимости оба `CComAggObject` и `CComObject` в модуле. Один `CComPolyObject` объект обрабатывает случаи, статистические и неагрегированные.

- [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) реализует `IUnknown` неагрегированные объекта, не изменяя счетчик блокировки модуля.

- [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) реализует `IUnknown` для перемещаемой интерфейса.

- [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) реализует `IUnknown` для интерфейса «кешированные» перемещаемой.

- [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) реализует `IUnknown` для внутреннего объекта агрегата или интерфейсом перемещаемой.

- [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) управляет, счетчик ссылок в модуле, чтобы обеспечить объект не будет удален.

- [CComObjectStack](../atl/reference/ccomobjectstack-class.md) создает временный объект COM, с помощью базовой реализации `IUnknown`.

## <a name="related-articles"></a>Связанные статьи

[Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)<br/>
[Макросы агрегирования и фабрик классов](../atl/reference/aggregation-and-class-factory-macros.md)<br/>
[Макросы сопоставления COM](../atl/reference/com-map-macros.md)<br/>
[Глобальные функции сопоставления COM](../atl/reference/com-map-global-functions.md)
