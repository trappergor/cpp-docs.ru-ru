---
title: "Преобразование не поддерживается поставщиком данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3dff3b8a7041c24f5becedb207b1aa9a9193afbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="converting-data-not-supported-by-the-provider"></a>Преобразование данных, не поддерживаемых поставщиком
Если потребитель запрашивает тип данных, который не поддерживается поставщиком, код шаблона поставщика OLE DB `IRowsetImpl::GetData` вызывает Msdadc.dll для преобразования типа данных.  
  
 При реализации интерфейса, аналогичного `IRowsetChange` , требует преобразования данных, вы можете вызвать Msdaenum.dll для выполнения преобразования. Используйте `GetData`, определенный в Atldb.h в качестве примера.  
  
## <a name="see-also"></a>См. также  
 [Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)