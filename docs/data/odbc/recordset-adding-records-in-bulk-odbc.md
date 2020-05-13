---
title: Набор записей. Добавление нескольких записей (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: f561cb0275933a973e97ef0518148e81e14a0234
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213022"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Набор записей. Добавление нескольких записей (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

Класс MFC [CRecordset](../../mfc/reference/crecordset-class.md) имеет новую оптимизацию, которая повышает эффективность при добавлении в таблицу новых записей.

> [!NOTE]
> Этот раздел относится к объектам, производным от `CRecordset`, в которых пакетное получение строк не реализовано. Если используется многострочная выборка строк, см. раздел [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Новый параметр для параметра *двоптионс* функции-члена [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) , `optimizeBulkAdd`, повышает производительность при последовательном добавлении нескольких записей без вызова `Requery` или `Close`. Только те поля, которые являются "грязными" до первого вызова `Update`, помечаются как "грязные" для последующих вызовов `AddNew`/`Update`.

Если вы используете классы базы данных, чтобы воспользоваться преимуществами функции API `::SQLSetPos` ODBC для добавления, изменения и удаления записей, такая оптимизация не требуется.

Если библиотека курсоров ODBC загружена или драйвер ODBC не поддерживает добавление, изменение и удаление с помощью `::SQLSetPos`, эта оптимизация повышает производительность. Чтобы включить эту оптимизацию, установите параметр *двоптионс* в вызове `Open` для набора записей следующим образом:

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>См. также раздел

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Набор записей. Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Набор записей. Блокировка (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
