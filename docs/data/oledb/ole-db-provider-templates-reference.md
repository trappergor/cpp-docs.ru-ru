---
title: Ссылка на шаблоны поставщика OLE DB
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
ms.openlocfilehash: f0200f0cff5292a75ec853496a644c148c8356a3
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545795"
---
# <a name="ole-db-provider-templates-reference"></a>Ссылка на шаблоны поставщика OLE DB

Классы и интерфейсы для шаблонов поставщика OLE DB можно сгруппировать в следующие категории. Справочные материалы также содержат сведения о [макросах для шаблонов поставщиков OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md).

Классы используют следующее соглашение об именовании: класс с именем с шаблоном `IWidgetImpl` предоставляющую реализацию `IWidget`интерфейса.

## <a name="session-classes"></a>Классы сеанса

[IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)<br/>
Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс во вновь созданном сеансе. Обязательный интерфейс для объектов источника данных.

[ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)<br/>
Реализует свойства сеанса путем вызова статической функции, определенной в сопоставлении набора свойств. Схема набора свойств должна быть указана в классе сеанса. Обязательный интерфейс в сеансах.

## <a name="rowset-classes"></a>Классы наборов строк

[CRowsetImpl](../../data/oledb/crowsetimpl-class.md)

Предоставляет стандартную реализацию набора строк OLE DB, не требуя множественного наследования многих интерфейсов реализации. Единственный метод, для которого необходимо предоставить реализацию, — это `Execute`.

[CSimpleRow](../../data/oledb/csimplerow-class.md)<br/>
Предоставляет реализацию по умолчанию для маркера строки, который используется в классе `IRowsetImpl`. Маркер строки логически является уникальным тегом для результирующей строки. `IRowsetImpl` создает новую `CSimpleRow` для каждой строки, запрашиваемой в `IRowsetImpl::GetNextRows`.

[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)<br/>
OLE DB требует, чтобы поставщики реализовали `HACCESSOR`, который является тегом массива структур `DBBINDING`. Предоставляет `HACCESSOR`s, которые являются адресами структур `BindType`. Обязательно для наборов строк и команд.

[IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)<br/>
Делегаты для статической функции, определяемой картой столбцов поставщика. Обязательный интерфейс для наборов строк и команд.

[иконверттипеимпл](../../data/oledb/iconverttypeimpl-class.md)<br/>
Предоставляет сведения о доступности преобразований типов в команде или в наборе строк. Обязателен для команд, наборов строк и наборов строк индекса. Реализует интерфейс `IConvertType` путем делегирования объекту преобразования, предоставленному OLE DB.

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)<br/>
Реализует интерфейс `IDBSchemaRowset` и функцию преобразованный Creator `CreateSchemaRowset`.

[IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)<br/>
Открывает и возвращает набор строк, включающий все строки из одной базовой таблицы или индекса. Обязательный интерфейс для объекта Session.

[ировсетчанжеимпл](../../data/oledb/irowsetchangeimpl-class.md)<br/>
Реализует интерфейс OLE DB [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) , который позволяет обновлять значения столбцов в существующих строках, удалять строки и вставлять новые строки.

[IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)<br/>
Этот класс наследует от [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) и переопределяет [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite). `IRowsetCreatorImpl` выполняет те же функции, что и `IObjectWithSite` но также включает свойства OLE DB `DBPROPCANSCROLLBACKWARDS` и `DBPROPCANFETCHBACKWARDS`.

[IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)<br/>
Реализует интерфейс `IRowsetIdentity`, который позволяет сравнить, являются ли две строки данных идентичными.

[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)<br/>
Предоставляет реализацию интерфейса `IRowset`, который является базовым интерфейсом набора строк.

[IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)<br/>
Реализует свойства набора строк с помощью схемы набора свойств, определенной в классе команд. Обязательный интерфейс для наборов строк.

[IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)<br/>
Реализует интерфейс OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) , который извлекает произвольные строки из набора строк. Чтобы обеспечить поддержку OLE DB закладок в наборе строк, сделайте набор строк производным от этого класса.

[IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)<br/>
Реализует широковещательные функции для уведомления прослушивателей на точке подключения `IID_IRowsetNotify` изменения содержимого набора строк. Потребители, обрабатывающие уведомления, реализуют [IRowsetNotify клиента](/previous-versions/windows/desktop/ms712959(v=vs.85)) и регистрируют их в этой точке подключения.

[IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)<br/>
Реализует интерфейс OLE DB [IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) , позволяющий потребителям откладывать передачу изменений, внесенных с помощью [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) , в источник данных и отменяя изменения перед передачей.

## <a name="command-classes"></a>Классы команд

[ICommandImpl](../../data/oledb/icommandimpl-class.md)<br/>
Предоставляет реализацию интерфейса `ICommand`. Этот интерфейс не отображается, но обрабатывается `ICommandTextImpl`. Обязательный интерфейс для объекта Command.

[ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)<br/>
Эта реализация интерфейса `ICommandProperties` предоставляется статической функцией, определяемой макросом `BEGIN_PROPSET_MAP`. Обязательный для команд.

[ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)<br/>
Задает, сохраняет и возвращает текст команды. Обязательный для команд.

[идбкреатекоммандимпл](../../data/oledb/idbcreatecommandimpl-class.md)<br/>
Создает новую команду из объекта Session и возвращает запрошенный интерфейс для вновь созданной команды. Необязательный интерфейс для объектов Session.

Другими классами команд являются `IColumnsInfoImpl` и `IAccessorImpl`, описанные выше в разделе классы наборов строк.

## <a name="data-source-classes"></a>Классы источников данных

[идбинитиализеимпл](../../data/oledb/idbinitializeimpl-class.md)<br/>
Создает и удаляет соединение с потребителем. Обязательный интерфейс для объектов источника данных и необязательный интерфейс для перечислителей.

[IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)<br/>
`IDBProperties` является обязательным интерфейсом для объектов источника данных и необязательным интерфейсом для перечислителей. Однако если перечислитель предоставляет `IDBInitialize`, он должен предоставлять доступ к `IDBProperties` (свойствам в источнике данных).

[ижетдатасаурцеимпл](../../data/oledb/igetdatasourceimpl-class.md)<br/>
Получает указатель интерфейса на объект источника данных. Обязательный интерфейс в сеансе.

## <a name="other-classes"></a>Другие классы

[CUtlProps](../../data/oledb/cutlprops-class.md)<br/>
Реализует свойства для различных интерфейсов свойств OLE DB (например, `IDBProperties`, `ISessionProperties`и `IRowsetInfo`).

[IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)

Реализует интерфейс OLE DB [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) , добавляя записи в элемент данных и получая их из него.

## <a name="see-also"></a>См. также:

[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Шаблоны OLE DB](../../data/oledb/ole-db-templates.md)