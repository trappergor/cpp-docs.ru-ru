---
title: Классы баз данных библиотеки ATL (шаблоны OLE DB)
ms.date: 05/02/2019
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: dc016a5e1e1d9652f6a69f73b5760f42dec5e889
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222567"
---
# <a name="atl-database-classes-ole-db-templates"></a>Классы баз данных библиотеки ATL (шаблоны OLE DB)

Корпорация Майкрософт предоставляет несколько реализаций OLE DB, набор COM-интерфейсов, обеспечивающих унифицированный доступ к данным в различных источниках и форматах.

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
