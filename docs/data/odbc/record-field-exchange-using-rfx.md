---
title: 'Обмен данными с полями записей: Использование RFX'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: 70197d2a9130388e86bb94f0d670360bb35febeb
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075868"
---
# <a name="record-field-exchange-using-rfx"></a>Обмен данными с полями записей: Использование RFX

В этом разделе объясняется, как использовать RFX в отношении того, что делает платформа.

> [!NOTE]
>  Этот раздел относится к классам, производным от [CRecordset](../../mfc/reference/crecordset-class.md) , в котором не реализована многострочная выборка строк. Если вы используете пакетное получение строк, реализуется пакетный обмен полями записей (Bulk RFX). Bulk RFX аналогичен RFX. Сведения о различиях см. в разделе [набор записей: незначительная выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Следующие разделы содержат связанные сведения:

- [Обмен данными с полями записей. Работа с кодом мастера](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) содержит основные компоненты RFX и объясняет код, который мастер приложений MFC и **Добавляет класс** (как описано в разделе [Добавление объекта-получателя MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) для поддержки RFX и как может потребоваться изменить код мастера.

- [Обмен данными с полями записей. Использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) объясняет, как записывать вызовы функций RFX в переопределение `DoFieldExchange`.

В следующей таблице показана роль в зависимости от того, что делает платформа.

### <a name="using-rfx-you-and-the-framework"></a>Использование RFX: вы и платформа

|Вы|Платформа|
|---------|-------------------|
|Объявите классы набора записей с помощью мастера. Укажите имена и типы данных для элементов данных полей.|Мастер создает класс `CRecordset` и записывает переопределение [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) , включая вызов функции RFX для каждого элемента данных поля.|
|Используемых Вручную добавьте в класс все необходимые элементы данных параметров. Вручную добавьте вызов функции RFX в `DoFieldExchange` для каждого элемента данных параметра, добавьте вызов [кфиелдексчанже:: сетфиелдтипе](../../mfc/reference/cfieldexchange-class.md#setfieldtype) для группы параметров и укажите общее число параметров в [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams). См. раздел [набор записей. Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).||
|Используемых Вручную привяжите дополнительные столбцы к элементам данных полей. Вручную увеличить [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields). См. раздел [набор записей. динамическое связывание столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||
|Создайте объект класса Recordset. Перед использованием объекта установите значения его элементов данных параметров, если они есть.|Для повышения эффективности платформа предвязывает параметры с помощью ODBC. При передаче значений параметров платформа передает их в источник данных. Для запросов передаются только значения параметров, кроме случаев, когда строки фильтра сортировки и (или) не изменились.|
|Откройте объект набора записей с помощью метода [CRecordset:: Open](../../mfc/reference/crecordset-class.md#open).|Выполняет запрос набора записей, привязывает столбцы к элементам данных полей набора записей и вызывает `DoFieldExchange` для обмена данными между первой выбранной записью и элементами данных поля набора записей.|
|Прокрутите набор записей с помощью метода [CRecordset:: Move](../../mfc/reference/crecordset-class.md#move) или команды меню или панели инструментов.|Вызывает `DoFieldExchange` для перемещения данных в элемент данных поля из новой текущей записи.|
|Добавление, обновление и удаление записей.|Вызывает `DoFieldExchange` для перемещения данных в источник данных.|

## <a name="see-also"></a>См. также:

[Обмен данными полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Обмен данными с полями записей. Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Набор записей. Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Класс CFieldExchange](../../mfc/reference/cfieldexchange-class.md)<br/>
[Макросы, глобальные функции и глобальные переменные](../../mfc/reference/mfc-macros-and-globals.md)
