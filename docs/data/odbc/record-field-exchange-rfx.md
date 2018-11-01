---
title: Обмен данными полями записей (RFX)
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
ms.openlocfilehash: f612f4be726707681ffbddff88ccc6b8a672e427
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522412"
---
# <a name="record-field-exchange-rfx"></a>Обмен данными полями записей (RFX)

Классы баз данных MFC ODBC автоматизируют перемещение данных между источником данных и [записей](../../data/odbc/recordset-odbc.md) объекта. При наследовании от класса [CRecordset](../../mfc/reference/crecordset-class.md) и выборка строк не используется, данные передаются с помощью механизма полями записей (RFX) exchange.

> [!NOTE]
>  Если вы реализовали выборка строк в производном `CRecordset` класс, инфраструктура использует механизм массового полями записей exchange (Bulk RFX) для передачи данных. Дополнительные сведения см. в разделе [набор записей: получение записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

RFX похож на обмен данными диалоговых окон (DDX). Перемещение данных между источником данных и элементами данных полей набора записей требует несколько вызовов в набор записей [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) и серьезного взаимодействия между платформой и [ODBC](../../data/odbc/odbc-basics.md). Механизм RFX является строго типизированным и избавляет от вызова функций ODBC, такие как `::SQLBindCol`. Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

RFX по большей части прозрачна для вас. Если вы объявите классов набора записей с помощью мастера приложений MFC или **Добавление класса** (как описано в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)), RFX встраивается в них автоматически. Класс набора записей должен быть производным от базового класса `CRecordset` предоставляемого платформой. Мастер приложений MFC позволяет создать класс начального набора записей. **Добавьте класс** позволяет добавлять другие классы набора записей, их при необходимости. Дополнительные сведения и примеры см. в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

Необходимо вручную добавить небольшой объем кода RFX в трех случаях, когда требуется:

- Используйте параметризованные запросы. Дополнительные сведения см. в разделе [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

- Выполнение соединений (с помощью одного набора записей для столбцов из двух или более таблиц). Дополнительные сведения см. в разделе [набор записей: выполнение Join (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).

- Динамическая привязка столбцов данных. Это реже, чем параметризации. Дополнительные сведения см. в разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

Если требуется хорошее представление о RFX см. в разделе [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).

В следующих разделах описаны сведения об использовании объекта набора записей:

- [Обмен данными с полями записей. Использование RFX](../../data/odbc/record-field-exchange-using-rfx.md)

- [Обмен полями записей. Использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

- [Обмен данными с полями записей. Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)

## <a name="see-also"></a>См. также

[Интерфейс ODBC](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Потребление MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Поддержка базы данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)