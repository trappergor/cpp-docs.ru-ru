---
title: Свойства и свойства страницы классов (ATL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.properties
dev_langs:
- C++
helpviewer_keywords:
- property pages, classes
- properties [ATL], classes
- properties [ATL]
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c71ca9412c9db86421c586c0602eb8e6548df622
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766757"
---
# <a name="properties-and-property-pages-classes"></a>Свойства и классы страниц свойств

Следующие классы поддерживают свойства и страницы свойств:

- [CComDispatchDriver](../atl/reference/atl-typedefs.md#ccomdispatchdriver) извлекает или задает свойства объекта с помощью `IDispatch` указатель.

- [CStockPropImpl](../atl/reference/cstockpropimpl-class.md) реализует стандартных свойств, поддерживаемых ATL.

- [IPerPropertyBrowsingImpl](../atl/reference/iperpropertybrowsingimpl-class.md) обращается к сведениям на страницах свойств объекта.

- [IPersistPropertyBagImpl](../atl/reference/ipersistpropertybagimpl-class.md) хранит свойства объекта в контейнер свойств, предоставляемых клиентом.

- [IPropertyPageImpl](../atl/reference/ipropertypageimpl-class.md) управляет заданной страницы свойств в окне свойств.

- [IPropertyPage2Impl](../atl/reference/ipropertypage2impl-class.md) аналогичен `IPropertyPageImpl`, но также позволяет клиенту выбора конкретного свойства в окне свойств.

- [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md) получает CLSID для страниц свойств, поддерживаемых объектом.

## <a name="related-articles"></a>Связанные статьи

[Учебник по ATL](../atl/active-template-library-atl-tutorial.md)

[Страницы свойств COM в ATL](../atl/atl-com-property-pages.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)   
[Макросы сопоставления свойств](../atl/reference/property-map-macros.md)

