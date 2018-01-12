---
title: "Свойства и свойства страницы классов (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.properties
dev_langs: C++
helpviewer_keywords:
- property pages, classes
- properties [ATL], classes
- properties [ATL]
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b6615f09245f4be3d5d98d1507b238c3b0d7b94c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="properties-and-property-pages-classes"></a>Свойства и классы страниц свойств
Следующие классы поддерживают свойства и страницы свойств:  
  
-   [CComDispatchDriver](../atl/reference/atl-typedefs.md#ccomdispatchdriver) Получает или задает свойства объекта с помощью `IDispatch` указателя.  
  
-   [CStockPropImpl](../atl/reference/cstockpropimpl-class.md) реализует стандартных свойств, поддерживаемых ATL.  
  
-   [IPerPropertyBrowsingImpl](../atl/reference/iperpropertybrowsingimpl-class.md) получает доступ к сведениям на страницах свойств объекта.  
  
-   [IPersistPropertyBagImpl](../atl/reference/ipersistpropertybagimpl-class.md) хранит свойства объекта в контейнер свойств, предоставленное клиентом.  
  
-   [IPropertyPageImpl](../atl/reference/ipropertypageimpl-class.md) управляет конкретную страницу свойств в окне свойств.  
  
-   [IPropertyPage2Impl](../atl/reference/ipropertypage2impl-class.md) аналогичен `IPropertyPageImpl`, но также позволяет клиенту выбрать определенное свойство на странице свойств.  
  
-   [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md) получает CLSID для страниц свойств, поддерживаемые объектом.  
  
## <a name="related-articles"></a>Связанные статьи  
 [Учебник по ATL](../atl/active-template-library-atl-tutorial.md)  
  
 [Страницы свойств COM в ATL](../atl/atl-com-property-pages.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../atl/atl-class-overview.md)   
 [Макросы сопоставления свойств](../atl/reference/property-map-macros.md)

