---
title: Интерфейсы объекта команды
ms.date: 10/24/2018
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
ms.openlocfilehash: 755c44cf8d0cb5bf5066197bfd0ead3e0f25e1f9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032405"
---
# <a name="command-object-interfaces"></a>Интерфейсы объекта команды

Объект команды использует `IAccessor` интерфейса для указания привязок параметров. Потребитель вызывает метод `IAccessor::CreateAccessor`, передавая ему массив `DBBINDING` структуры. `DBBINDING` содержит сведения о привязках к столбцам (например, тип и длина). Поставщик получает структуры и определяет, как данные должны передаваться и нужны ли преобразования.

`ICommandText` Интерфейс обеспечивает способ определения текстовой команды. `ICommandProperties` Интерфейс обрабатывает все свойства команд.

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
