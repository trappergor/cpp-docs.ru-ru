---
title: 'Обмен данными с полями записей: Использование RFX'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: dc0cdcee758f4842b0738068a8a11c4e2e404155
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367146"
---
# <a name="record-field-exchange-using-rfx"></a>Обмен данными с полями записей: Использование RFX

Эта тема объясняет, что вы делаете, чтобы использовать RFX по отношению к тому, что делает фреймворк.

> [!NOTE]
> Эта тема относится к классам, полученным из [CRecordset,](../../mfc/reference/crecordset-class.md) в которых объем строки извлечения не был реализован. Если вы используете пакетное получение строк, реализуется пакетный обмен полями записей (Bulk RFX). Bulk RFX аналогичен RFX. Чтобы понять различия, [см.](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

Следующие темы содержат соответствующую информацию:

- [Запись поле обмена: Работа с Волшебник код](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) вводит основные компоненты RFX и объясняет код, который MFC приложение Мастера и **добавить класса** (как описано в [Добавлении MFC ODBC Consumer](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) написать для поддержки RFX и как вы можете изменить код мастера.

- [Обмен полязаписи: Использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) объясняет написание вызовов функциям RFX в вашем `DoFieldExchange` переопределение.

В следующей таблице показана ваша роль по отношению к тому, что фреймворк делает для вас.

### <a name="using-rfx-you-and-the-framework"></a>Использование RFX: Вы и рамки

|Вы|Платформа|
|---------|-------------------|
|Объявить свои классы рекордов с мастером. Указать имена и типы данных членов полевых данных.|Мастер получает `CRecordset` класс и записывает переопределение [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) для вас, включая вызов функции RFX для каждого члена данных поля.|
|(Необязательно) Вручную добавляйте в класс необходимые параметры. Вручную добавьте вызов функции RFX `DoFieldExchange` для каждого члена параметра данных, добавьте вызов в [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) для группы параметров и укажите общее количество параметров в [m_nParams.](../../mfc/reference/crecordset-class.md#m_nparams) [См. Рекордсет: Параметрынс-сет (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).||
|(Необязательно) Вручную привязать дополнительные столбцы к полевым членам данных. Ручное приращение [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields). [См. Запись: Динамически связывающие столбцы данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||
|Создайте объект класса записей. Перед использованием объекта установите значения его параметров членов данных, если таковые имеются.|Для эффективности, фреймворк предуродив параметры, используя ODBC. При прохождении значений параметров фреймворк передает их источнику данных. Только значения параметров отправляются на перезапросии, если только строки сортировки и/или фильтра не изменились.|
|Откройте объект регистрации с помощью [CRecordset::Open](../../mfc/reference/crecordset-class.md#open).|Выполняет запрос записи, связывает столбцы с полевыми членами данных `DoFieldExchange` в наборе записей и призывает обмениваться данными между первой выбранной записью и членами полевых данных.|
|Прокрутите в наборе рекордов с помощью [CRecordset::Move](../../mfc/reference/crecordset-class.md#move) или команды меню или панели инструментов.|Призывы `DoFieldExchange` к передаче данных полевым членам данных из новой текущей записи.|
|Добавляйте, обновляйте и удаляйте записи.|Призывы `DoFieldExchange` к передаче данных в источник данных.|

## <a name="see-also"></a>См. также раздел

[Рекордная полевая биржа (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Обмен данными с полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Набор записей. Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Класс CFieldExchange](../../mfc/reference/cfieldexchange-class.md)<br/>
[Макросы, глобальные функции и глобальные переменные](../../mfc/reference/mfc-macros-and-globals.md)
