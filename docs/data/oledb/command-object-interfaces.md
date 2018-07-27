---
title: Интерфейсы объекта команды | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 9c597cc30e23ffce2787eac6c13f6ba8c53f96c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096123"
---
# <a name="command-object-interfaces"></a>Интерфейсы объекта команды
Объект команды использует `IAccessor` интерфейс для указания привязок параметров. Потребитель вызывает метод `IAccessor::CreateAccessor`, передавая ему массив `DBBINDING` структуры. `DBBINDING` содержит сведения о привязках к столбцам (например, тип и длина). Поставщик получает структуры и определяет способ передачи данных и нужны ли преобразования.  
  
 `ICommandText` Интерфейс обеспечивает способ определения текстовой команды. `ICommandProperties` Интерфейс обрабатывает все свойства команд.  
  
## <a name="see-also"></a>См. также  
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)