---
title: Ссылка на шаблоны поставщика OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 42909a9ddc24131c759886c4d169c4fd7484ca98
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340421"
---
# <a name="ole-db-provider-templates-reference"></a>Ссылка на шаблоны поставщика OLE DB
Классы и интерфейсы для шаблонов поставщика OLE DB могут быть сгруппированы в следующие категории. Справочные материалы также включает информацию о [макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md).  
  
 Классы используют следующее соглашение об именовании: класс с именем в формате `IWidgetImpl` бы предоставить реализацию интерфейса `IWidget`.  
  
## <a name="session-classes"></a>Классы сеансов  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс на вновь созданный сеанс. Обязательный интерфейс для объектов источника данных.  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 Реализует свойства сеанса путем вызова статического функции, определенные сопоставлением набора свойств. Сопоставление набора свойств должен быть указан в классе сеанса. Обязательный интерфейс для сеансов.  
  
## <a name="rowset-classes"></a>Классы набора строк  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 Предоставляет стандартную реализацию набора строк OLE DB без необходимости множественное наследование, многие реализации интерфейсов. Единственный метод, для которого необходимо предоставить реализацию `Execute`.  
  
 [CSimpleRow](../../data/oledb/csimplerow-class.md)  
 Предоставляет реализацию по умолчанию для дескриптора строки, которая используется в `IRowsetImpl` класса. Дескриптор строки логически является уникальный маркер для строки результата. `IRowsetImpl` Создает новый `CSimpleRow` для каждой строки запроса в `IRowsetImpl::GetNextRows`.  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB требует, чтобы поставщики для реализации `HACCESSOR`, который является тегом в массив `DBBINDING` структуры. Предоставляет `HACCESSOR`, которые являются адресами `BindType` структуры. Обязателен для наборов строк и команд.  
  
 [IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 Делегаты к статической функции, определенные схемой сопоставления столбца поставщика. Обязательный интерфейс для наборов строк и команд.  
  
 [IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)  
 Сведения о доступности преобразований типа команды или для набора строк. Обязателен для команд, наборов строк и наборов строк индекса. Реализует `IConvertType` интерфейс путем делегирования для преобразования объекта, заданного параметром OLE DB.  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 Реализует `IDBSchemaRowset` интерфейс и шаблонизируемую функцию создателя `CreateSchemaRowset`.  
  
 [IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)  
 Открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса. Обязательный интерфейс для объекта сеанса.  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 Реализует OLE DB [IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx) интерфейс, позволяющий обновлять значения столбцов в существующих строках, удаление строк и вставки новых строк.  
  
 [IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)  
 Этот класс наследует от [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) и переопределяет [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). `IRowsetCreatorImpl` выполняет те же функции, что `IObjectWithSite` , но и обеспечивает свойства OLE DB `DBPROPCANSCROLLBACKWARDS` и `DBPROPCANFETCHBACKWARDS`.  
  
 [IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)  
 Реализует `IRowsetIdentity` интерфейс, который позволяет сравнивать ли две строки данных идентичны, или нет.  
  
 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)  
 Предоставляет реализацию `IRowset` интерфейс, который является базовый интерфейс набора строк.  
  
 [IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)  
 Реализует свойства набора строк с помощью свойства набора карты, определенные в классе команды. Обязательный интерфейс наборов строк.  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 Реализует OLE DB [IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx) интерфейс, который извлекает строки из набора строк. Поддерживает закладки OLE DB в наборе строк, чтобы наследовать от этого класса набора строк.  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 Реализует широковещательных функции для в точке подключения `IID_IRowsetNotify` об изменениях содержимого набора строк. Реализовать потребителей, обработки уведомлений [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx) и зарегистрируйте его на эту точку подключения.  
  
 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)  
 Реализует OLE DB [IRowsetUpdate](https://msdn.microsoft.com/library/ms714401.aspx) интерфейс, который позволяет потребителям приостановить передачу изменений, внесенных с [IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx) для источника данных и отменить изменения перед передачей.  
  
## <a name="command-classes"></a>Классы команд  
 [ICommandImpl](../../data/oledb/icommandimpl-class.md)  
 Предоставляет реализацию интерфейса `ICommand`. Этот интерфейс не отображается, но обрабатывается `ICommandTextImpl`. Обязательный интерфейс объекта команды.  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 Эта реализация `ICommandProperties` интерфейс предоставляется статические функции, определенной на `BEGIN_PROPSET_MAP` макрос. Обязателен для команды.  
  
 [ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)  
 Задает, хранит и возвращает текст команды. Обязателен для команды.  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 Создает новую команду из объекта сеанса и возвращает запрошенный интерфейс на созданная команда. Дополнительный интерфейс для объектов сеанса.  
  
 Другие классы команд имеют `IColumnsInfoImpl` и `IAccessorImpl`, описанные в предыдущем разделе классы набора строк.  
  
## <a name="data-source-classes"></a>Классы источника данных  
 [IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)  
 Создает и удаляет подключение к получателю. Обязательный интерфейс на объекты источника данных и дополнительный интерфейс для перечислителей.  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` — обязательный интерфейс для объектов источников данных и дополнительный интерфейс для перечислителей. Тем не менее если перечислитель предоставляет `IDBInitialize`, она должна предоставлять `IDBProperties` (свойства источника данных).  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 Получает указатель интерфейса на объект источника данных. Обязательный интерфейс в сеансе.  
  
## <a name="other-classes"></a>Другие классы  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 Реализует свойства для различных интерфейсов свойство OLE DB (например, `IDBProperties`, `ISessionProperties`, и `IRowsetInfo`).  
  
 [IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 Реализует OLE DB [IErrorRecords](https://msdn.microsoft.com/library/ms718112.aspx) интерфейс, добавления записей и извлечения записей из элемента данных.  
  
## <a name="see-also"></a>См. также  
 [Ссылка на шаблоны OLE DB потребителя](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Шаблоны OLE DB](../../data/oledb/ole-db-templates.md)