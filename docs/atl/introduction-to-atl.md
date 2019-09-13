---
title: Введение в ATL
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM objects, creating in ATL
- ATL
ms.assetid: 77f565e8-c4ec-4a80-af4b-7278fcfe5c98
ms.openlocfilehash: 5eba816bc87eeebea2c41489a5d15c48645739e8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492105"
---
# <a name="introduction-to-atl"></a>Введение в ATL

ATL — это библиотека активных шаблонов, набор классов на основе C++ шаблонов, с помощью которых можно легко создавать небольшие, быстрые объекты модели компонентов (com). Она имеет специальную поддержку ключевых возможностей com, включая следующие акции: стандартные реализации [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown), [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory), [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)и `IDispatch`; сдвоенные интерфейсы перечислителя com; точки подключения, разрывы интерфейс и элементы управления ActiveX.

Код ATL можно использовать для создания однопотоковых объектов, объектов модели-контейнера, объектов модели свободных потоков, а также для объектов модели с произвольным потоком и потоковым контейнером.

В этом разделе рассматриваются следующие темы:

- Отличия [библиотеки шаблонов](../atl/using-a-template-library.md) от стандартной библиотеки.

- Что вы [можете и не можете делать с помощью ATL](../atl/scope-of-atl.md).

- [Рекомендации по выбору между ATL и MFC](../atl/recommendations-for-choosing-between-atl-and-mfc.md).

## <a name="see-also"></a>См. также

[Введение в модель COM и ATL](../atl/introduction-to-com-and-atl.md)
