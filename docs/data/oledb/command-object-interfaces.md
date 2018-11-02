---
title: Интерфейсы объекта команды
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: d9f663d4e857d300e5c0f5783b86445ce824ea8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598878"
---
# <a name="command-object-interfaces"></a>Интерфейсы объекта команды

Объект команды использует `IAccessor` интерфейса для указания привязок параметров. Потребитель вызывает метод `IAccessor::CreateAccessor`, передавая ему массив `DBBINDING` структуры. `DBBINDING` содержит сведения о привязках к столбцам (например, тип и длина). Поставщик получает структуры и определяет, как данные должны передаваться и нужны ли преобразования.

`ICommandText` Интерфейс обеспечивает способ определения текстовой команды. `ICommandProperties` Интерфейс обрабатывает все свойства команд.

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
