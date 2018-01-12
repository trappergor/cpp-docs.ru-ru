---
title: "Усовершенствование простого поставщика только для чтения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ad1ccd39ff66e4c193364549f58c78c6b743af0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="enhancing-the-simple-read-only-provider"></a>Усовершенствование простого поставщика только для чтения
В этом разделе показано, как улучшить [простого поставщика только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md) создан в предыдущем разделе. `IRowsetLocateImpl`Создает реализацию `IRowsetLocate` интерфейс и добавляет поддержку закладки для вас.  
  
 При наличии действующий поставщик, может потребоваться расширить его возможности для обеспечения обновления, обработки транзакций или повышения производительности алгоритма выборки строк. Большинство поставщика усовершенствования включают Добавление интерфейса в существующий объект COM.  
  
 В примере в следующих разделах улучшает механизма выборки строк путем добавления `IRowsetLocate` интерфейс `CAgentRowset`. В разделах показано, как для:  
  
-   [Сделать RMyProviderRowset наследовать IRowsetLocate](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).  
  
-   [Динамически определить столбцы, возвращенные объекту-получателю](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>См. также  
 [Создание простого поставщика только для чтения](../../data/oledb/creating-a-simple-read-only-provider.md)