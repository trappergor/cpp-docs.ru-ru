---
title: 'Элементы управления ATL: Общие вспомогательные классы'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
ms.openlocfilehash: c3d6f7588e333a27a8bc766d982660aaa4d984c9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818613"
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
