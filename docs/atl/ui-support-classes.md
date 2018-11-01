---
title: Классы с поддержкой пользовательского интерфейса (ATL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.ui
helpviewer_keywords:
- user interfaces, support classes
- user interfaces, ATL classes
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
ms.openlocfilehash: 7306ddbbc3cf70850e0c7c66e48abf402017e5db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644229"
---
# <a name="ui-support-classes"></a>Классы с поддержкой пользовательского интерфейса

Перечисленные ниже классы предоставляют общие поддержка пользовательского интерфейса:

- [IDocHostUIHandlerDispatch](../atl/reference/idochostuihandlerdispatch-interface.md) интерфейс для синтаксического анализа Microsoft HTML и механизм визуализации.

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) предоставляет основные методы, через которые контейнер взаимодействует с элементом управления. Управляет активацией и деактивацией встроенных элементов управления на месте.

- [IOleInPlaceObjectWindowlessImpl](../atl/reference/ioleinplaceobjectwindowlessimpl-class.md) управляет повторной активации элементов управления на месте. Позволяет элементу управления без окон для получения сообщений, а также участвовать в операциях перетаскивания и вставки.

- [IOleInPlaceActiveObjectImpl](../atl/reference/ioleinplaceactiveobjectimpl-class.md) помогает связи между элементом управления на месте и его контейнером.

- [IViewObjectExImpl](../atl/reference/iviewobjecteximpl-class.md) позволяет элементу управления отображаться непосредственно и для уведомления о контейнере изменений в его отображение. Поддерживает рисование без мелькания, непрямоугольные и прозрачные элементы управления и проверке нажатия.

## <a name="related-articles"></a>Связанные статьи

[Учебник по ATL](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)

