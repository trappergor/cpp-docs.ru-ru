---
title: ': Набор записей | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7bb39b910eae797f360513954ad0c32d5e99bb86
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089289"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Набор записей. Добавление нескольких записей (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 MFC [CRecordset](../../mfc/reference/crecordset-class.md) класс имеет новый оптимизации, который позволяет повысить эффективность при добавлении новых записей в пакетном режиме в таблицу.  
  
> [!NOTE]
>  Этот раздел относится к объектам, производным от `CRecordset` в какой строке массовая выборка не был реализован. Если используется выборка строк, см. раздел [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Новый параметр для **dwOptions** параметр [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) функции-члена **optimizeBulkAdd**, улучшает производительность при добавлении нескольких записей последовательное построение без вызова **Requery** или **закрыть**. Только поля, которые являются "грязными" до первого **обновление** вызова, помечаются как "грязные" при последующих `AddNew` / **обновление** вызовов.  
  
 Если вы используете классы баз данных пользоваться преимуществами **:: SQLSetPos** функции ODBC API для добавления, изменения и удаления записей, эта оптимизация не требуется.  
  
 Если загружается библиотека курсоров ODBC или драйвер ODBC не поддерживает добавление, изменение и удаление с помощью **:: SQLSetPos**, эта оптимизация повысит массового добавления производительности. Чтобы включить данную оптимизацию, установите **dwOptions** параметр в **откройте** вызова для следующего набора записей:  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Набор записей: Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Набор записей. Блокировка (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)