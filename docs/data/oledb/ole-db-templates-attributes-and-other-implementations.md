---
title: Шаблоны, атрибуты и другие реализации OLE DB
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
ms.openlocfilehash: 0e6b5dbc97f6a7bea1df342d6a792ea43907ca33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283897"
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>Шаблоны, атрибуты и другие реализации OLE DB

## <a name="atl-ole-db-templates"></a>Шаблоны ATL OLE DB

Шаблоны OLE DB, которые являются частью ATL (Active Template Library), упрощают технологии высокой производительности баз данных OLE DB путем предоставления классов, реализующих многие часто используемые интерфейсы OLE DB. Вместе с этот шаблон библиотека поставляется поддержка мастера для создания начальных приложений OLE DB.

Библиотека шаблонов состоит из двух частей:

- **Шаблоны потребителей OLE DB** используется для реализации приложения клиент (потребитель) OLE DB.

- **Шаблоны поставщика OLE DB** используется для реализации приложения сервера (поставщик) OLE DB.

Чтобы использовать шаблоны OLE DB, необходимо иметь навыки работы с шаблонами C++, COM и интерфейсами OLE DB. Если вы не знакомы с OLE DB, см. в разделе [Справочник программиста OLE DB по](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming).

Дополнительные сведения вы можете:

- Ознакомьтесь с разделами о [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md) или [шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md).

- Создание [потребителя OLE DB](../../data/oledb/creating-an-ole-db-consumer.md) или [поставщик OLE DB](../../data/oledb/creating-an-ole-db-provider.md).

- См. в списке [классы потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) или [классы поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md).

- См. в списке [примеры шаблонов OLE DB](https://github.com/Microsoft/VCSamples).

- См. в разделе [справочнике программиста OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) (в Windows SDK).

## <a name="ole-db-attributes"></a>Атрибуты OLE DB

[Атрибуты потребителя OLE DB](../../windows/ole-db-consumer-attributes.md) предоставляют удобный способ создания потребителей OLE DB. Эти атрибуты OLE DB внедряют код на основе [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) для создания рабочих потребителей OLE DB и поставщиков. Если вам нужно указать функциональные возможности, не поддерживаемые атрибуты, можно использовать шаблоны OLE DB в сочетании с атрибутами в коде.

## <a name="mfc-ole-db-classes"></a>Классы MFC OLE DB

Библиотека MFC содержит один класс [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), которая отображает записи базы данных в элементах управления. Представление — представление формы, который напрямую подключен к `CRowset` и отображает поля `CRowset` в элементах управления шаблона диалогового окна. Он также предоставляет реализацию по умолчанию для перехода к первой, далее, предыдущих или последних записей и интерфейс для обновления записи в данный момент в представлении. Дополнительные сведения см. в разделе `COleDBRecordView`.

## <a name="ole-db-sdk-interfaces"></a>Интерфейсы OLE DB SDK

В случаях, когда шаблоны OLE DB не поддерживает функциональные возможности OLE DB необходимо использовать сами интерфейсы OLE DB. Дополнительные сведения см. в разделе [Справочник программиста OLE DB по](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) в пакете Windows SDK.

## <a name="see-also"></a>См. также

[Программирование объектов OLE DB](../../data/oledb/ole-db-programming.md)<br/>
[Общие сведения о программировании OLE DB](../../data/oledb/ole-db-programming-overview.md)