---
title: Создание простого поставщика только для чтения
ms.date: 10/26/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
ms.openlocfilehash: a80678f6bc512c45c0df2ea5cbfc4708f1252ac0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362004"
---
# <a name="creating-a-simple-read-only-provider"></a>Создание простого поставщика только для чтения

После создания поставщика OLE DB с помощью **мастер проектов ATL** и **мастер поставщика ATL OLE DB**, можно добавить другие функциональные возможности, которые должны поддерживаться. Начните разработку вашего поставщика с помощью проверки какие данные вы отправим объекту-получателю и при каких условиях. Это особенно важно определить, требуется ли поддержка команд, транзакций и других дополнительных объектов. Качественная разработка поставщика будет быструю реализацию и тестирование.

Пример состоит из двух частей:

- В первой части показан как [создание простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md) , который считывает пары строк.

- Вторая часть показывает как [улучшения простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md) , добавив `IRowsetLocate` интерфейс.

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
