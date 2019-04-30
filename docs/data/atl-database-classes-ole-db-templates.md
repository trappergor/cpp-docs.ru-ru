---
title: Классы баз данных библиотеки ATL (шаблоны OLE DB)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: 2ecde060f10a7c2a056869525f58d0bb4da67963
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393822"
---
# <a name="atl-database-classes-ole-db-templates"></a>Классы баз данных библиотеки ATL (шаблоны OLE DB)

Корпорация Майкрософт предоставляет несколько реализаций OLE DB, набор COM-интерфейсов, обеспечивающих унифицированный доступ к данным в различных источниках и форматах.  OLE DB обычно не используется; Данный документ предназначен для разработчиков, которые Поддержка устаревшего кода. Новые приложения должны использовать ODBC для подключения к источникам данных SQL.

Шаблоны OLE DB являются шаблонами C++ ATL, которые упрощают технологии баз данных OLE DB для использования, предоставляя классов, реализующих многие часто используемые интерфейсы OLE DB.

Библиотека шаблонов состоит из двух частей:

- [Шаблоны потребителей OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md) используется для реализации приложения клиент (потребитель) OLE DB.

- [Шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-cpp.md) используется для реализации приложения сервера (поставщик) OLE DB.

Кроме того [атрибуты потребителя OLE DB](../windows/ole-db-consumer-attributes.md) предоставляют удобный способ создания потребителей OLE DB. Эти атрибуты OLE DB внедряют код, основанный на шаблонах потребителей OLE DB для создания рабочих потребителей OLE DB.

Обратите внимание, что библиотека MFC содержит один класс [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), которая отображает записи базы данных в элементах управления. Представление — представление формы, который напрямую подключен к `CRowset` и отображает поля `CRowset` в элементах управления шаблона диалогового окна.

Дополнительные сведения см. в разделе [OLE DB программирования](../data/oledb/ole-db-programming.md) и [Руководство программиста OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming).

## <a name="see-also"></a>См. также

[Создание объекта-получателя OLE DB](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[Создание поставщика OLE DB](../data/oledb/creating-an-ole-db-provider.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Ссылка на шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Примеры шаблонов OLE DB](https://github.com/Microsoft/VCSamples)