---
title: Шаблоны, атрибуты и другие реализации OLE DB
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
ms.openlocfilehash: 217db304c7d0b5723b7af383e07290f160cc9465
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500914"
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>Шаблоны, атрибуты и другие реализации OLE DB

## <a name="atl-ole-db-templates"></a>Шаблоны OLE DB ATL

Шаблоны OLE DB, которые являются частью ATL (библиотека активных шаблонов), упрощают использование высокопроизводительной OLE DB технологии баз данных, предоставляя классы, реализующие многие из часто используемых интерфейсов OLE DB. Вместе с этой библиотекой шаблонов появилась поддержка мастера создания приложений OLE DB Starter.

Эта библиотека шаблонов содержит две части:

- **Шаблоны потребителей OLE DB** Используется для реализации приложения OLE DB клиента (потребителя).

- **Шаблоны поставщика OLE DB** Используется для реализации приложения OLE DB Server (поставщик).

Чтобы использовать шаблоны OLE DB, необходимо иметь навыки работы с шаблонами C++, COM и интерфейсами OLE DB. Если вы не знакомы с OLE DB, см. статью [OLE DB Справочник программиста](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming).

Дополнительные сведения можно получить с:

- Ознакомьтесь с разделами о [шаблонах OLE DB потребителей](../../data/oledb/ole-db-consumer-templates-cpp.md) или [шаблонах поставщиков OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md).

- Создание [OLE DB потребителя](../../data/oledb/creating-an-ole-db-consumer.md) или [поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md).

- См. список классов [OLE DB потребителей](../../data/oledb/ole-db-consumer-templates-reference.md) или [классов поставщиков OLE DB](../../data/oledb/ole-db-provider-templates-reference.md).

- См. список [примеров шаблонов OLE DB](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB).

- См. раздел [Справочник программиста OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) (в Windows SDK).

## <a name="ole-db-attributes"></a>Атрибуты OLE DB

[OLE DB атрибуты потребителя](../../windows/attributes/ole-db-consumer-attributes.md) предоставляют удобный способ создания OLE DB потребителей. OLE DB атрибуты вставляют код на основе [шаблонов OLE DB потребителей](../../data/oledb/ole-db-consumer-templates-reference.md) для создания рабочих OLE DB потребителей и поставщиков. Если необходимо указать функциональные возможности, которые не поддерживаются атрибутами, можно использовать шаблоны OLE DB в сочетании с атрибутами в коде.

## <a name="mfc-ole-db-classes"></a>Классы MFC OLE DB

Библиотека MFC имеет один класс [коледбрекордвиев](../../mfc/reference/coledbrecordview-class.md), который отображает записи базы данных в элементах управления. Представление является представлением формы, которое напрямую подключено к `CRowset` объекту и отображает поля `CRowset` объекта в элементах управления шаблона диалогового окна. Он также предоставляет реализацию по умолчанию для перехода к первой, следующей, предыдущей или последней записи и интерфейс для обновления записи в данный момент в представлении. Для получения дополнительной информации см. `COleDBRecordView`.

## <a name="ole-db-sdk-interfaces"></a>Интерфейсы пакета SDK OLE DB

В случаях, когда шаблоны OLE DB не поддерживают функции OLE DB, необходимо использовать сами интерфейсы OLE DB. Дополнительные сведения см. в разделе [Справочник программистов OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[OLE DB программирование](../../data/oledb/ole-db-programming.md)<br/>
[Общие сведения о программировании OLE DB](../../data/oledb/ole-db-programming-overview.md)
