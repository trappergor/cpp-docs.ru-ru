---
title: Интерфейсы объекта команды | Документация Майкрософт
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command object interfaces [C++]
- command objects [OLE DB]
- OLE DB [C++], command object interfaces
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f5d09e5794b66895d4bfd6a12fe7b0e1dbeeea7f
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216335"
---
# <a name="command-object-interfaces"></a>Интерфейсы объекта команды

Объект команды использует `IAccessor` интерфейса для указания привязок параметров. Потребитель вызывает метод `IAccessor::CreateAccessor`, передавая ему массив `DBBINDING` структуры. `DBBINDING` содержит сведения о привязках к столбцам (например, тип и длина). Поставщик получает структуры и определяет, как данные должны передаваться и нужны ли преобразования.

`ICommandText` Интерфейс обеспечивает способ определения текстовой команды. `ICommandProperties` Интерфейс обрабатывает все свойства команд.

## <a name="see-also"></a>См. также

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
