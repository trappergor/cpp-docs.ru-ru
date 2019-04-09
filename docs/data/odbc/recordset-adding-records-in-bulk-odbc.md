---
title: Набор записей. Добавление записей (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: a2c3eab8bb4c0e8db76fceb5a2dafd16a4a07079
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038613"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Набор записей. Добавление записей (ODBC)

Этот раздел относится к классам ODBC библиотеки MFC.

MFC [CRecordset](../../mfc/reference/crecordset-class.md) класс имеет добавлены средства оптимизации позволяет повысить эффективность при добавлении новых записей в пакетном режиме в таблицу.

> [!NOTE]
> Этот раздел относится к объектам, производным от `CRecordset` в какой строке массовой выборка не был реализован. Если вы используете выборка строк, см. в разделе [набор записей: Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Новый параметр для *dwOptions* параметр [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) функции-члена `optimizeBulkAdd`, улучшает производительность при добавлении нескольких записей последовательно без вызова `Requery` или `Close`. Только те поля, которые "грязные" перед первым `Update` вызов помечаются как "грязный" для последующих `AddNew` / `Update` вызовов.

Если вы используете классы баз данных пользоваться преимуществами `::SQLSetPos` функции ODBC API для добавления, редактирования и удаления записей, эта оптимизация не требуется.

Если загружается библиотека курсоров ODBC или драйвер ODBC не поддерживает добавление, изменение и удаление с помощью `::SQLSetPos`, эта оптимизация повысит Массовое добавление производительности. Чтобы включить такую оптимизацию, установите *dwOptions* параметр в `Open` вызова для набора записей следующее:

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>См. также

[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Набор записей. Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Набор записей. Блокировка записей (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)