---
title: "Набор записей (ODBC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- recordsets, snapshots
- recordsets, creating
- dynamic recordsets
- forward-only recordsets
- recordsets, dynasets
- ODBC recordsets, CRecordset objects
- ODBC recordsets
- recordsets, about recordsets
- snapshots, ODBC recordsets
- dynasets
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2c5fc714b9c2ff0e1af679edbc3842b86d201fee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-odbc"></a>Набор записей (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 Объект [CRecordset](../../mfc/reference/crecordset-class.md) представляет набор записей, выбранных из источника данных. Записи можно из:  
  
-   Таблица.  
  
-   Запрос.  
  
-   Хранимая процедура, которая обращается к одной или нескольких таблиц.  
  
 Пример набора записей на основе таблицы — «все клиенты», которая обращается к таблице клиентов. Пример запроса — «все счета конкретного лица.» Пример объекта recordset, основанного на хранимую процедуру (иногда называется предопределенного запроса) — «все учетные записи оплачен,» который вызывает хранимую процедуру в базе данных серверной части. Набор записей можно объединить две или более таблиц из одного источника данных, но не к таблицам из различных источников данных.  
  
> [!NOTE]
>  Сведения о создании производных классов записей с помощью мастеров см. в разделе [Добавление потребителя ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) и [Поддержка баз данных, мастер приложений MFC](../../mfc/reference/database-support-mfc-application-wizard.md).  
  
> [!NOTE]
>  Некоторые драйверы ODBC поддерживают представления баз данных. Представление в этом смысле — запросов, созданных с помощью SQL `CREATE VIEW` инструкции. Мастера в настоящее время не поддерживает представления, но можно написать код самостоятельно.  
  
##  <a name="_core_recordset_capabilities"></a>Возможности наборов записей  
 Все объекты наборов записей обладают следующими возможностями:  
  
-   Если источник данных не только для чтения, можно указать, что набор записей быть [обновляемые](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), [добавление](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), или только для чтения. Если набор записей может обновляться, можно выбрать либо пессимистичного или оптимистичного [блокировки](../../data/odbc/recordset-locking-records-odbc.md) методы, предоставленные драйвер предоставляет соответствующий режим поддерживается. Если источник данных доступен только для чтения, набор записей будут доступны только для чтения.  
  
-   Элемент может вызывать функции для [прокрутки](../../data/odbc/recordset-scrolling-odbc.md) через выбранной записи.  
  
-   Вы можете [фильтра](../../data/odbc/recordset-filtering-records-odbc.md) записей выбранных записей.  
  
-   Вы можете [сортировки](../../data/odbc/recordset-sorting-records-odbc.md) записи в порядке возрастания или убывания, на основе одного или нескольких столбцов.  
  
-   Вы можете [параметризовать](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) recordset, выбранные во время выполнения.  
  
##  <a name="_core_snapshots_and_dynasets"></a>Моментальные снимки и динамические наборы  
 Существует два основных типа наборов записей: [моментальные снимки](../../data/odbc/snapshot.md) и [динамических подмножеств данных](../../data/odbc/dynaset.md). Оба поддерживаются классом `CRecordset`. Каждый совместно используются общие характеристики все наборы записей, но каждый расширяет общие функциональные возможности специализированные своему. Моментальные снимки статических данных и представление полезны для отчетов и других ситуациях, когда требуется представление данных на определенный момент времени. Динамические наборы предназначены для отображения изменения, сделанные другими пользователями, вносимых в набор записей, без необходимости повторный запрос или обновление набора записей. Моментальные снимки и динамические подмножества данных может быть обновляемым или только для чтения. Отражают записи, добавленные или удаленные другими пользователями, вызовите метод [метод CRecordset::Requery](../../mfc/reference/crecordset-class.md#requery).  
  
 `CRecordset`также поддерживает два типа наборов записей: динамические наборы записей и наборы последовательного доступа. Динамические наборы записей аналогичны динамических подмножеств данных; Однако динамические наборы записей отражают все записи добавлены или удалены без вызова `CRecordset::Requery`. По этой причине динамические наборы записей, обычно предъявляют по отношению к времени обработки на СУБД и не поддерживают многие драйверы ODBC. Напротив наборы записей последовательного доступа предоставляют наиболее эффективный метод доступа к данным для наборов записей, не требующих обновления или обратной прокрутки. Например можно использовать только вперед записей для переноса данных из одного источника данных в другую, когда вам требуется для перемещения по данным в прямом направлении. Чтобы воспользоваться последовательным записей, выполните оба следующих действия.  
  
-   Передать параметр **CRecordset::forwardOnly** как `nOpenType` параметр [откройте](../../mfc/reference/crecordset-class.md#open) функции-члена.  
  
-   Укажите **CRecordset::readOnly** в `dwOptions` параметр **откройте**.  
  
    > [!NOTE]
    >  Сведения о требованиях к драйверам ODBC для поддержки динамических подмножеств данных см. в разделе [ODBC](../../data/odbc/odbc-basics.md). Список драйверов ODBC, поставляемых в этой версии Visual C++ и сведения о приобретении дополнительных драйверов см. в разделе [список драйверов ODBC](../../data/odbc/odbc-driver-list.md).  
  
##  <a name="_core_your_recordsets"></a>Работа с наборами записей  
 Для каждого отдельных таблиц, представление или хранимую процедуру, необходимо получить доступ, обычно определяется класс, производный от `CRecordset`. (Исключением является соединения базы данных, в которой один набор записей представляет столбцы из нескольких таблиц.) При наследовании класса набора записей, включить механизм обмена (полями записей RFX) полями записей или механизм обмена (полями записей Bulk RFX) массового поле записи, которые похожи на механизм обмена (DDX) данных диалогового окна. RFX и Bulk RFX позволяют упростить передачу данных из источника данных в набор записей. RFX также поддерживает передачу данных из набора записей в источнике данных. Дополнительные сведения см. в разделе [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md) и [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Объект набора записей обеспечивает доступ для всех выбранных записях. Прокрутите записи с помощью `CRecordset` функций-членов, таких как `MoveNext` и `MovePrev`. В то же время объекта набора записей представляет только один из выбранных записей текущей записи. Можно просмотреть поля текущей записи, объявив записей переменные-члены класса, соответствующие столбцам таблицы или записей, которые являются результатом запроса к базе данных. Сведения о членах данных набора записей см. в разделе [набор записей: архитектура (ODBC)](../../data/odbc/recordset-architecture-odbc.md).  
  
 В следующих разделах описаны сведения об использовании объекта набора записей. Разделы, перечислены в функциональные категории и порядке для разрешения последовательное чтение.  
  
### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>Разделы, посвященные механизм, позволяющий открытие, чтение и закрытие наборов записей  
  
-   [Набор записей. Архитектура (ODBC)](../../data/odbc/recordset-architecture-odbc.md)  
  
-   [Набор записей. Объявление класса таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)  
  
-   [Набор записей. Создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)  
  
-   [Набор записей. Прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)  
  
-   [Набор записей. Закладки и абсолютное позиционирование (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)  
  
-   [Набор записей. Фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)  
  
-   [Набор записей. Сортировка записей (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)  
  
-   [Набор записей. Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>Разделы, посвященные изменение наборов записей  
  
-   [Набор записей. Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)  
  
-   [Набор записей. Блокировка (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)  
  
-   [Набор записей. Выполнение обновления наборов записей (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)  
  
### <a name="topics-about-somewhat-more-advanced-techniques"></a>Разделы, посвященные немного дополнительные возможности  
  
-   [Набор записей. Объединение (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)  
  
-   [Набор записей. Объявление класса для предопределенного запроса (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)  
  
-   [Набор записей. Динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)  
  
-   [Набор записей. Пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)  
  
-   [Набор записей. Работа с большими элементами данных (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md)  
  
-   [Набор записей. Определение сумм и других статистических результатов (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)  
  
### <a name="topics-about-how-recordsets-work"></a>Разделы, посвященные работе наборы записей  
  
-   [Набор записей. Порядок выборки записей в наборе (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)  
  
-   [Набор записей. Порядок обновления записей в наборе (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)  
  
## <a name="see-also"></a>См. также  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Потребление MFC ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Транзакция (ODBC)](../../data/odbc/transaction-odbc.md)