---
title: "Реализация IUnknown классов (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.Iunknown
dev_langs: C++
helpviewer_keywords: IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ac484e58b585a09eff40d1b058e44dad6b8d394c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="iunknown-implementation-classes"></a>Классы реализации IUnknown
Следующие классы реализуют **IUnknown** и связанные методы:  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) управляет подсчетом ссылок для статистическим и неагрегированные объектов. Позволяет указать потоковую модель.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) управляет подсчетом ссылок для статистическим и неагрегированные объектов. Использует значение по умолчанию потоковая модель сервера.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) реализует **IUnknown** для вычисляемого объекта.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) реализует **IUnknown** неагрегированные объекта.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) реализует **IUnknown** статистические и нестатистические объекта. С помощью `CComPolyObject` позволяет избежать оба `CComAggObject` и `CComObject` в модуле. Один `CComPolyObject` объект обрабатывает статистическим и неагрегированные вариантов.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) реализует **IUnknown** неагрегированные объекта, не изменяя счетчик блокировки модуля.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) реализует **IUnknown** перемещаемые интерфейса.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) реализует **IUnknown** для интерфейса «кешированные» перемещаемые.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) реализует **IUnknown** для агрегата или интерфейс перемещаемые внутренний объект.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) управляет подсчет ссылок для модуля, чтобы обеспечить объект не будет удалена.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) создает временный объект COM с использованием базовой реализации **IUnknown**.  
  
## <a name="related-articles"></a>Связанные статьи  
 [Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../atl/atl-class-overview.md)   
 [Агрегирование и макросы фабрики класса](../atl/reference/aggregation-and-class-factory-macros.md)   
 [Макросы схемы COM](../atl/reference/com-map-macros.md)   
 [Глобальные функции сопоставления COM](../atl/reference/com-map-global-functions.md)

