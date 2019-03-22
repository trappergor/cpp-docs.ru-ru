---
title: Программирование объектов OLE DB
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB [C++]
- data access [C++], OLE DB programming
- OLE DB [C++], about OLE DB
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
ms.openlocfilehash: fccf9ee553160d687a6094ccc9b95f4c55f7094f
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328549"
---
# <a name="ole-db-programming"></a>Программирование объектов OLE DB

Microsoft OLE DB — это устаревшая технология; для новых приложений это требуется API доступа к данным для связанных серверов SQL. Все другие новые приложения должны использовать ODBC. Текущий поставщик OLE DB для SQL Server — SQLNCLI11. БИБЛИОТЕКА DLL. Поставщик по-прежнему продается в SQL Server 2016. Эта документация предназначена для разработчиков, которые поддержки существующих приложений, которые уже используют OLE DB.

Шаблоны OLE DB являются шаблонами C++, которые упрощают использование технологии баз данных OLE DB с высокой производительностью за счет использования классов, реализующих многие часто используемые интерфейсы OLE DB. Библиотека шаблонов состоит из шаблонов клиента и шаблонов поставщика.

Visual C++ также включает поддержку мастера для создания начальных приложений OLE DB.

Кроме того можно использовать атрибуты для реализации шаблонов потребителей OLE DB.

|Для получения дополнительных сведений о|См.|
|-------------------------|---------|
|Использование пользовательских шаблонов OLE DB (основные разделы)|[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)|
|Использование шаблонов поставщика OLE DB (основные разделы)|[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)|
|Классы и макросы шаблонов OLE DB|[Ссылка на шаблоны OLE DB](../../data/oledb/ole-db-templates.md) (Visual C++)|
|Атрибуты пользователя OLE DB|[Атрибуты объекта-получателя OLE DB](../../windows/ole-db-consumer-attributes.md)|
|Интерфейсы OLE DB|[Справочник программиста OLE DB](/sql/connect/oledb/oledb-driver-for-sql-server) (в пакете Windows SDK)|
|Примеры шаблонов OLE DB|[Примеры шаблонов OLE DB](https://github.com/Microsoft/VCSamples)|
|Общие сведения о программировании доступа к данным (Visual C++)|[Программирование доступа к данным](../../data/data-access-programming-mfc-atl.md)|
|Основные разделы ODBC|[Интерфейс ODBC](../../data/odbc/open-database-connectivity-odbc.md)|

## <a name="see-also"></a>См. также

[Доступ к данным](../data-access-in-cpp.md)