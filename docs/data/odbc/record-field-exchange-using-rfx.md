---
title: 'Обмен данными с полями записей: Использование RFX'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: 8d8ba1e66c1ffc46429b5c0e987be833aef2e72f
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328541"
---
# <a name="record-field-exchange-using-rfx"></a>Обмен данными с полями записей: Использование RFX

В этом разделе описано использование RFX относительно и среды.

> [!NOTE]
>  Этот раздел относится к классам, производным от [CRecordset](../../mfc/reference/crecordset-class.md) в какой строке массовой выборка не был реализован. Если вы используете выборка строк, реализуется блочный обмен полей записей (Bulk RFX). Bulk RFX аналогичен RFX. Сведения о различиях, см. в разделе [набор записей: получение записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Следующие разделы содержат связанные сведения:

- [Обмен полями записей: Работа с кодом мастера](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) представлены основные компоненты RFX и описывает код, мастер приложений MFC и **Добавление класса** (как описано в разделе [Добавление потребителя ODBC MFC ](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) для поддержки RFX и способ изменения кода мастера.

- [Обмен полями записей: Использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) описывает написание вызовов функций RFX в вашей `DoFieldExchange` переопределить.

В следующей таблице показаны роли по отношению к, что платформа делает за вас.

### <a name="using-rfx-you-and-the-framework"></a>Использование RFX: Вы и платформа

|Вы|Платформа|
|---------|-------------------|
|Объявление классов набора записей с помощью мастера. Укажите имена и типы данных элементов данных полей.|Мастер создает производный `CRecordset` класса и записи [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) для переопределения, включая RFX-функции вызова для каждого элемента данных поля.|
|(Необязательно) Вручную добавьте в класс членов данных необходимых параметров. Вручную добавьте вызов функции RFX для `DoFieldExchange` для каждого элемента данных параметра, добавьте вызов [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) для группы параметров и укажите общее число параметров в [m_nParams ](../../mfc/reference/crecordset-class.md#m_nparams). См. в разделе [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).||
|(Необязательно) Вручную привязать дополнительные столбцы с элементами данных полей. Вручную увеличить [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields). См. в разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||
|Создайте объект класса набора записей. Перед использованием объекта, задайте значения параметра данные-члены, если таковые имеются.|Для повышения эффективности среда повторно связывает параметры, с помощью ODBC. При передаче значения параметров, среда передает их в источник данных. Только значения параметров отправляются для повторных запросов, если строки сортировки и/или фильтр были изменены.|
|Откройте объект набора записей с помощью [CRecordset::Open](../../mfc/reference/crecordset-class.md#open).|Выполняет запрос набора записей, связывает столбцы с элементами данных полей набора записей, а также вызывает `DoFieldExchange` для обмена данными между первой выбранной записи и поля элементов данных набора записей.|
|Прокрутки в наборе записей с помощью [CRecordset::Move](../../mfc/reference/crecordset-class.md#move) или команду меню или панели инструментов.|Вызовы `DoFieldExchange` для передачи данных в поля элементов данных из новой текущей записи.|
|Добавление, обновление и удаление записей.|Вызовы `DoFieldExchange` для передачи данных в источнике данных.|

## <a name="see-also"></a>См. также

[Обмен данными полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Обмен данными с полями записей. Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Набор записей. Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Класс CFieldExchange](../../mfc/reference/cfieldexchange-class.md)<br/>
[Макросы, глобальные функции и глобальные переменные](../../mfc/reference/mfc-macros-and-globals.md)

