---
title: 'Элементов управления ATL: Общие вспомогательные классы'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.controls
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
ms.openlocfilehash: 49b7ff751db33ce2647ea7d4865ebea93949813b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551441"
---
# <a name="controls-general-support-classes"></a>Элементы управления: Общие вспомогательные классы

Перечисленные ниже классы предоставляют общую поддержку для элементов управления ATL:

- [CComControl](../atl/reference/ccomcontrol-class.md) состоит из вспомогательных функций и данным-членам, которые необходимы для элементов управления ATL.

- [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) предоставляет методы, необходимые для элементов управления.

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) предоставляет основные методы, через которые контейнер взаимодействует с элементом управления. Управляет активацией и деактивацией встроенных элементов управления на месте.

- [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) объединяет инициализации в один вызов, чтобы помочь избежать задержек при загрузке элементов управления контейнеров.

- [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) предоставляет взаимодействия с минимальными мышью для элемента управления, в противном случае неактивной.

## <a name="sample-program"></a>Пример программы

[ATLFire](../visual-cpp-samples.md)

## <a name="related-articles"></a>Связанные статьи

[Учебник по ATL](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)

