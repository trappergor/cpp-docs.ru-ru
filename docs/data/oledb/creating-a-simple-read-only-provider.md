---
title: Создание простого поставщика только для чтения
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: c0f31818002ce4611926d942b3bc556e31c1ae6f
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524715"
---
# <a name="creating-a-simple-read-only-provider"></a>Создание простого поставщика только для чтения

::: moniker range="vs-2019"

Мастер поставщика OLE DB в ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="vs-2017"

После создания поставщика OLE DB с помощью **мастера проектов ATL** и **мастера поставщика OLE DB в ATL** вы можете добавить другие функциональные возможности, поддержку которых нужно обеспечить. Начните разработку вашего поставщика с изучения того, какие данные вы будете отправлять объекту-получателю и при каких условиях. Особенно важно определить, требуется ли поддержка команд, транзакций и других дополнительных объектов. Качественное планирование процесса ускорит реализацию и тестирование.

Пример разбит на две части:

- В первой части показано, как [создать простого поставщика с доступом только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md), который считывает пару строк.

- Во второй части показано, как [улучшить простого поставщика с доступом только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md), добавив интерфейс `IRowsetLocate`.

::: moniker-end

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
