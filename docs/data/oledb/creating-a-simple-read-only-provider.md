---
title: Создание простого поставщика только для чтения | Документация Майкрософт
ms.custom: ''
ms.date: 10/26/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: ade8ccdd-9ea4-4e46-a964-18460c2a2401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c8fd4e5eb25ab1e8e6b20b576a0688da7b5aa2ef
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216400"
---
# <a name="creating-a-simple-read-only-provider"></a>Создание простого поставщика только для чтения

После создания поставщика OLE DB с помощью **мастер проектов ATL** и **мастер поставщика ATL OLE DB**, можно добавить другие функциональные возможности, которые должны поддерживаться. Начните разработку вашего поставщика с помощью проверки какие данные вы отправим объекту-получателю и при каких условиях. Это особенно важно определить, требуется ли поддержка команд, транзакций и других дополнительных объектов. Качественная разработка поставщика будет быструю реализацию и тестирование.

Пример состоит из двух частей:

- В первой части показан как [создание простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md) , который считывает пары строк.

- Вторая часть показывает как [улучшения простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md) , добавив `IRowsetLocate` интерфейс.

## <a name="see-also"></a>См. также

[Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
