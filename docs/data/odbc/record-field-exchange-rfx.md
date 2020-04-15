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
ms.openlocfilehash: 6f965b90e1e0bbcfd3ad04bb5b40644d61050b2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367153"
---
# <a name="record-field-exchange-rfx"></a>Обмен данными полями записей (RFX)

Классы базы данных MFC ODBC автоматизируют перемещение данных между источником данных и объектом [регистрации.](../../data/odbc/recordset-odbc.md) Когда вы получаете класс из [CRecordset](../../mfc/reference/crecordset-class.md) и не используете объемную строку извлечения, данные передаются механизмом обмена поля записи (RFX).

> [!NOTE]
> Если вы реализовали объемстроки, `CRecordset` извлекающей в производный класс, фреймворк использует механизм обмена полями массовых записей (Bulk RFX) для передачи данных. Для получения дополнительной информации [см. Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

RFX похож на диалоговые данные (DDX). Перемещение данных между источником данных и полевыми членами данных в наборе записей требует нескольких вызовов функции [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) в записи и значительного взаимодействия между инфраструктурой и [ODBC.](../../data/odbc/odbc-basics.md) Механизм RFX является безопасным для типов и экономит вам работу `::SQLBindCol`вызова функций ODBC, таких как . Дополнительные сведения об DDX см [обмен данными окон и проверка](../../mfc/dialog-data-exchange-and-validation.md).

RFX в основном прозрачныдля для вас. Если вы объявляете свои классы рекордов с MFC Application Wizard или **добавляете класс** (как описано в [Добавлении Потребительm MFC),](../../mfc/reference/adding-an-mfc-odbc-consumer.md)RFX встраивается в них автоматически. Класс записей должен быть выведен из `CRecordset` базового класса, поставляемого рамкой. Мастер приложений MFC позволяет создать начальный класс рекордсета. **Добавить класс** позволяет добавлять другие классы записей, как вам это нужно. Для получения дополнительной информации и примеров, [см. Добавление MFC ODBC потребителей](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

Вы должны вручную добавить небольшое количество кода RFX в трех случаях, когда вы хотите:

- Используйте параметризированные запросы. Для получения дополнительной информации [см.](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

- Выполните соединения (с помощью одного набора записей для столбцов из двух или более таблиц). Для получения дополнительной информации [см.](../../data/odbc/recordset-performing-a-join-odbc.md)

- Динамически связывайте столбцы данных. Это встречается реже, чем параметризация. Для получения дополнительной информации [см. Recordset: Динамически связывающие столбцы данных (ODBC).](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

Если вам нужно более глубокое понимание RFX, [см.](../../data/odbc/record-field-exchange-how-rfx-works.md)

Следующие темы объясняют детали использования объектов звукозаписи:

- [Обмен данными с полями записей: Использование RFX](../../data/odbc/record-field-exchange-using-rfx.md)

- [Обмен полями записей. Использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

- [Обмен данными с полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)

## <a name="see-also"></a>См. также раздел

[Открытая связь с базами данных (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Потребление MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Поддержка базы данных, Мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
