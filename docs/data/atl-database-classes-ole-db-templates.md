---
title: Классы баз данных библиотеки ATL (шаблоны OLE DB)
ms.date: 05/02/2019
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: 76e9f49d4b394d0c807ca1f3d103ff325ded8a09
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213503"
---
# <a name="atl-database-classes-ole-db-templates"></a>Классы баз данных библиотеки ATL (шаблоны OLE DB)

Корпорация Майкрософт предоставляет несколько реализаций OLE DB, набор COM-интерфейсов, обеспечивающих единообразный доступ к данным в различных источниках и форматах информации.

Шаблоны OLE DB — C++ это шаблоны в библиотеке ATL, которые упрощают использование технологии OLE DB баз данных, предоставляя классы, реализующие многие из часто используемых интерфейсов OLE DB.

Эта библиотека шаблонов содержит две части:

- [Шаблоны потребителей OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md) Используется для реализации приложения OLE DB клиента (потребителя).

- [Шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-cpp.md) Используется для реализации приложения OLE DB Server (поставщик).

Кроме того, [OLE DB атрибуты потребителя](../windows/ole-db-consumer-attributes.md) предоставляют удобный способ создания OLE DB потребителей. Атрибуты OLE DB вставляют код на основе шаблонов потребителей OLE DB для создания рабочих OLE DB потребителей.

Обратите внимание, что библиотека MFC содержит один класс [коледбрекордвиев](../mfc/reference/coledbrecordview-class.md), который отображает записи базы данных в элементах управления. Представление является представлением формы, которое напрямую подключено к `CRowset` объекту, и отображает поля объекта `CRowset` в элементах управления шаблона диалогового окна.

Дополнительные сведения см. в разделе [OLE DB программирование](../data/oledb/ole-db-programming.md) и [OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming).

## <a name="see-also"></a>См. также раздел

[Создание объекта-получателя OLE DB](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[Создание поставщика OLE DB](../data/oledb/creating-an-ole-db-provider.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Ссылка на шаблоны поставщика OLE DB](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Примеры шаблонов OLE DB](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB)
