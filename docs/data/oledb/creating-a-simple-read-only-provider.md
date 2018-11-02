---
title: Создание простого поставщика только для чтения
ms.date: 10/26/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: 2ac8e45ca06a5566923141adf5a22dc6710eeeab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432608"
---
# <a name="creating-a-simple-read-only-provider"></a>Создание простого поставщика только для чтения

После создания поставщика OLE DB с помощью **мастер проектов ATL** и **мастер поставщика ATL OLE DB**, можно добавить другие функциональные возможности, которые должны поддерживаться. Начните разработку вашего поставщика с помощью проверки какие данные вы отправим объекту-получателю и при каких условиях. Это особенно важно определить, требуется ли поддержка команд, транзакций и других дополнительных объектов. Качественная разработка поставщика будет быструю реализацию и тестирование.

Пример состоит из двух частей:

- В первой части показан как [создание простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md) , который считывает пары строк.

- Вторая часть показывает как [улучшения простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md) , добавив `IRowsetLocate` интерфейс.

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
