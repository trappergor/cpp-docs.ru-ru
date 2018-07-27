---
title: Классы для реализации IUnknown (ATL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.Iunknown
dev_langs:
- C++
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4cd2f2473249271285d6b8812dac1b924e5a172
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848540"
---
# <a name="iunknown-implementation-classes"></a>Классы для реализации IUnknown
Следующие классы реализуют `IUnknown` и связанными методами:  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) управляет подсчетом ссылок для статистическим и неагрегированные объектов. Позволяет указать потоковую модель.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) управляет подсчетом ссылок для статистическим и неагрегированные объектов. Использует потоковую модель сервера по умолчанию.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) реализует `IUnknown` для объединенного объекта.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) реализует `IUnknown` неагрегированные объекта.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) реализует `IUnknown` для статистически обработанные и неагрегированные объектов. С помощью `CComPolyObject` избавляет от необходимости оба `CComAggObject` и `CComObject` в модуле. Один `CComPolyObject` объект обрабатывает случаи, статистические и неагрегированные.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) реализует `IUnknown` неагрегированные объекта, не изменяя счетчик блокировки модуля.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) реализует `IUnknown` для перемещаемой интерфейса.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) реализует `IUnknown` для интерфейса «кешированные» перемещаемой.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) реализует `IUnknown` для внутреннего объекта агрегата или интерфейсом перемещаемой.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) управляет, счетчик ссылок в модуле, чтобы обеспечить объект не будет удален.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) создает временный объект COM, с помощью базовой реализации `IUnknown`.  
  
## <a name="related-articles"></a>Связанные статьи  
 [Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../atl/atl-class-overview.md)   
 [Агрегирование и макросов фабрики класса](../atl/reference/aggregation-and-class-factory-macros.md)   
 [Макросы сопоставления COM](../atl/reference/com-map-macros.md)   
 [Глобальные функции сопоставления COM](../atl/reference/com-map-global-functions.md)

