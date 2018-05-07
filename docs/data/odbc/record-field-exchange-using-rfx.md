---
title: 'Обмен полями записей: Использование RFX | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 296ae2e4f535e08924a77b8726b93778a6da5026
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="record-field-exchange-using-rfx"></a>Обмен данными с полями записей: Использование RFX
В этом разделе описано использование RFX относительно и среды.  
  
> [!NOTE]
>  Этот раздел относится к классы, производные от [CRecordset](../../mfc/reference/crecordset-class.md) в какой строке массовая выборка не был реализован. Если вы используете выборка строк, реализуется блочный обмен полей записей (Bulk RFX). Bulk RFX аналогичен RFX. О различиях в разделе [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Следующие разделы содержат связанные сведения:  
  
-   [Обмен полями записей: Работа с кодом мастера](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) содержит сведения об основных компонентах RFX и описывает код, мастер приложений MFC и **добавить класс** (как описано в [Добавление потребителя ODBC MFC ](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) для поддержки RFX и способ изменения кода мастера.  
  
-   [Обмен полями записей: Использование функций RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) описывает написание вызовов функций RFX в вашей `DoFieldExchange` переопределения.  
  
 В следующей таблице показаны роль разработчика платформа делает за вас.  
  
### <a name="using-rfx-you-and-the-framework"></a>Использование RFX: Разработчик и среда  
  
|Вы|Платформа|  
|---------|-------------------|  

| Объявите классов набора записей с помощью мастера. Укажите имена и типы данных элементов данных полей. | Мастер создает производный `CRecordset` класса и записи [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) для переопределения, включая RFX функций вызова для каждого элемента данных поля. |  
| (Необязательно) Вручную добавьте в класс элементов данных необходимых параметров. Вручную добавьте вызов функции RFX для `DoFieldExchange` для каждого элемента данных параметра, добавьте вызов [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) для группы параметров и укажите общее число параметров в [m_nParams ](../../mfc/reference/crecordset-class.md#m_nparams). В разделе [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md). ||  
| (Необязательно) Члены данных полей вручную свяжите дополнительные столбцы. Вручную увеличивается [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields). В разделе [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). ||  

| Создание объекта класса набора записей. Перед использованием объекта, значения параметра элементы данных, если таковые имеются. | Для повышения эффективности среда повторно связывает параметры с помощью ODBC. При передаче значения параметра, среда передает их в источник данных. Для повторных запросов, отправляются только значения параметров, если строки сортировки и/или фильтр были изменены. |  
| Открытие объекта набора записей с помощью [CRecordset::Open](../../mfc/reference/crecordset-class.md#open). | Выполняет запрос набора записей, связывает столбцы с элементами данных полей набора записей и вызывает `DoFieldExchange` для обмена данными между первой выбранной записью и элементам данных полей. |  
| Прокрутки записей с помощью [CRecordset::Move](../../mfc/reference/crecordset-class.md#move) или команды меню или панели инструментов. | Вызовы `DoFieldExchange` передавать данные с элементами данных полей из новой текущей записи. |  
| Добавление, обновление и удаление записей. | Вызовы `DoFieldExchange` для передачи данных в источнике данных. |  
  
## <a name="see-also"></a>См. также  
 [Обмен полями записей (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [Обмен полями записей: Принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Набор записей: Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset-класс](../../mfc/reference/crecordset-class.md)   
 [Класс разделе](../../mfc/reference/cfieldexchange-class.md)   
 [Макросы, глобальные функции и глобальные переменные](../../mfc/reference/mfc-macros-and-globals.md)

