---
title: Преобразование не поддерживается поставщиком данных | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d0be19345ff6c425cfbc020f2096ca82680586d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095470"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Преобразование данных, не поддерживаемых поставщиком
Если потребитель запрашивает тип данных, который не поддерживается поставщиком, код шаблона поставщика OLE DB `IRowsetImpl::GetData` вызывает Msdadc.dll для преобразования типа данных.  
  
 При реализации интерфейса, аналогичного `IRowsetChange` , требует преобразования данных, вы можете вызвать Msdaenum.dll для выполнения преобразования. Используйте `GetData`, определенный в Atldb.h в качестве примера.  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)