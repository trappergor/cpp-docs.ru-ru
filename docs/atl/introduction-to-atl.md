---
title: Введение в ATL | Документация Майкрософт
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM objects, creating in ATL
- ATL
ms.assetid: 77f565e8-c4ec-4a80-af4b-7278fcfe5c98
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93baa57e8567b6ab08a0157f200a4d89fc9813e4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754846"
---
# <a name="introduction-to-atl"></a>Введение в ATL

ATL является Active Template Library, классы набора основанных на шаблонах C++ с помощью которого можно легко создавать небольших, быстрых объектов модели объектов компонента (COM). Он имеет специальную поддержку для основных компонентов COM, включая: биржевые реализации [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown), [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory), [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2), и `IDispatch`; двойной интерфейсы; Стандартные интерфейсы перечислителя COM; точки подключения; перемещаемые интерфейсы; и элементы управления ActiveX.

Код ATL можно использовать для создания однопоточными объектами, объекты модели подразделения, объекты модели свободных потоков или свободнопоточный и модели объектов.

В этом разделе рассматриваются:

- Как [библиотека шаблонов](../atl/using-a-template-library.md) отличается от стандартной библиотеки.

- Какие вы [могут делать с библиотекой ATL, а](../atl/scope-of-atl.md).

- [Рекомендации по выбору между ATL и MFC](../atl/recommendations-for-choosing-between-atl-and-mfc.md).

## <a name="see-also"></a>См. также

[Введение в модель COM и ATL](../atl/introduction-to-com-and-atl.md)

