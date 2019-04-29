---
title: Ссылка на шаблоны поставщика OLE DB
ms.date: 11/04/2016
f1_keywords:
- vc.templates.ole
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
ms.openlocfilehash: e1d6be9687085361edd9141d8fb471e21b6f6376
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283873"
---
# <a name="ole-db-provider-templates-reference"></a>Ссылка на шаблоны поставщика OLE DB

Классы и интерфейсы для шаблонов поставщика OLE DB могут быть сгруппированы в следующие категории. Справочные материалы также включает информацию о [макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md).

Классы используют следующее соглашение об именовании: класс с именем в формате `IWidgetImpl` бы предоставить реализацию интерфейса `IWidget`.

## <a name="session-classes"></a>Классы сеансов

[IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)<br/>
Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс на вновь созданный сеанс. Обязательный интерфейс для объектов источника данных.

[ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)<br/>
Реализует свойства сеанса путем вызова статического функции, определенные сопоставлением набора свойств. Сопоставление набора свойств должен быть указан в классе сеанса. Обязательный интерфейс для сеансов.

## <a name="rowset-classes"></a>Классы набора строк

[CRowsetImpl](../../data/oledb/crowsetimpl-class.md)

Предоставляет стандартную реализацию набора строк OLE DB без необходимости множественное наследование, многие реализации интерфейсов. Единственный метод, для которого необходимо предоставить реализацию `Execute`.

[CSimpleRow](../../data/oledb/csimplerow-class.md)<br/>
Предоставляет реализацию по умолчанию для дескриптора строки, которая используется в `IRowsetImpl` класса. Дескриптор строки логически является уникальный маркер для строки результата. `IRowsetImpl` Создает новый `CSimpleRow` для каждой строки запроса в `IRowsetImpl::GetNextRows`.

[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)<br/>
OLE DB требует, чтобы поставщики для реализации `HACCESSOR`, который является тегом в массив `DBBINDING` структуры. Предоставляет `HACCESSOR`, которые являются адресами `BindType` структуры. Обязателен для наборов строк и команд.

[IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)<br/>
Делегаты к статической функции, определенные схемой сопоставления столбца поставщика. Обязательный интерфейс для наборов строк и команд.

[IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)<br/>
Сведения о доступности преобразований типа команды или для набора строк. Обязателен для команд, наборов строк и наборов строк индекса. Реализует `IConvertType` интерфейс путем делегирования для преобразования объекта, заданного параметром OLE DB.

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)<br/>
Реализует `IDBSchemaRowset` интерфейс и шаблонизируемую функцию создателя `CreateSchemaRowset`.

[IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)<br/>
Открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса. Обязательный интерфейс для объекта сеанса.

[IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)<br/>
Реализует OLE DB [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) интерфейс, позволяющий обновлять значения столбцов в существующих строках, удаление строк и вставки новых строк.

[IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)<br/>
Этот класс наследует от [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) и переопределяет [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite). `IRowsetCreatorImpl` выполняет те же функции, что `IObjectWithSite` , но и обеспечивает свойства OLE DB `DBPROPCANSCROLLBACKWARDS` и `DBPROPCANFETCHBACKWARDS`.

[IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)<br/>
Реализует `IRowsetIdentity` интерфейс, который позволяет сравнивать ли две строки данных идентичны, или нет.

[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)<br/>
Предоставляет реализацию `IRowset` интерфейс, который является базовый интерфейс набора строк.

[IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)<br/>
Реализует свойства набора строк с помощью свойства набора карты, определенные в классе команды. Обязательный интерфейс наборов строк.

[IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)<br/>
Реализует OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) интерфейс, который извлекает строки из набора строк. Поддерживает закладки OLE DB в наборе строк, чтобы наследовать от этого класса набора строк.

[IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)<br/>
Реализует широковещательных функции для в точке подключения `IID_IRowsetNotify` об изменениях содержимого набора строк. Реализовать потребителей, обработки уведомлений [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) и зарегистрируйте его на эту точку подключения.

[IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)<br/>
Реализует OLE DB [IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) интерфейс, который позволяет потребителям приостановить передачу изменений, внесенных с [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) для источника данных и отменить изменения перед передачей.

## <a name="command-classes"></a>Классы команд

[ICommandImpl](../../data/oledb/icommandimpl-class.md)<br/>
Предоставляет реализацию интерфейса `ICommand`. Этот интерфейс не отображается, но обрабатывается `ICommandTextImpl`. Обязательный интерфейс объекта команды.

[ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)<br/>
Эта реализация `ICommandProperties` интерфейс предоставляется статические функции, определенной на `BEGIN_PROPSET_MAP` макрос. Обязателен для команды.

[ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)<br/>
Задает, хранит и возвращает текст команды. Обязателен для команды.

[IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)<br/>
Создает новую команду из объекта сеанса и возвращает запрошенный интерфейс на созданная команда. Дополнительный интерфейс для объектов сеанса.

Другие классы команд имеют `IColumnsInfoImpl` и `IAccessorImpl`, описанные в предыдущем разделе классы набора строк.

## <a name="data-source-classes"></a>Классы источника данных

[IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)<br/>
Создает и удаляет подключение к получателю. Обязательный интерфейс на объекты источника данных и дополнительный интерфейс для перечислителей.

[IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)<br/>
`IDBProperties` — обязательный интерфейс для объектов источников данных и дополнительный интерфейс для перечислителей. Тем не менее если перечислитель предоставляет `IDBInitialize`, она должна предоставлять `IDBProperties` (свойства источника данных).

[IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)<br/>
Получает указатель интерфейса на объект источника данных. Обязательный интерфейс в сеансе.

## <a name="other-classes"></a>Другие классы

[CUtlProps](../../data/oledb/cutlprops-class.md)<br/>
Реализует свойства для различных интерфейсов свойство OLE DB (например, `IDBProperties`, `ISessionProperties`, и `IRowsetInfo`).

[IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)

Реализует OLE DB [IErrorRecords](/previous-versions/windows/desktop/ms718112(v=vs.85)) интерфейс, добавления записей и извлечения записей из элемента данных.

## <a name="see-also"></a>См. также

[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Шаблоны OLE DB](../../data/oledb/ole-db-templates.md)