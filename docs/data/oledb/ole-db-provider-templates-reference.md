---
title: "Ссылка на шаблоны поставщика OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "шаблоны поставщика OLE DB"
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ссылка на шаблоны поставщика OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Классы и интерфейсы для шаблонов поставщика OLE DB можно группировать на следующие категории.  Опорный материал также приведены сведения о [макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md).  
  
 Классы используют следующее соглашение об именах: класс **IWidgetImpl** с шаблоном, предоставивший реализацию интерфейса **IWidget**.  
  
## Классы сеанса  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 Создает новый сеанс из объекта источника данных и возвращает запрошенный интерфейс в только что созданном объекте сеанса.  Обязательный интерфейс для объекта источника данных.  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 Реализует свойства сеанса, вызвав статическая функция определяется сопоставление набора свойств.  Сопоставление набора свойств должно быть указано в классе сеанса.  Обязательный интерфейс на сеансах.  
  
## Классы набора строк  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 Предоставляет стандартную реализацию набора строк OLE DB, без необходимости множественного наследования множество интерфейсов реализации.  Единственный метод, для которого необходимо предоставить реализацию **Выполнить**.  
  
 [CSimpleRow](../Topic/CSimpleRow%20Class.md)  
 Предоставляет реализацию по умолчанию для обработки строк, который используется в классе `IRowsetImpl`.  Дескриптор строки логически уникальный тег для строки результата.  `IRowsetImpl` создает новое `CSimpleRow` для каждой строки в запрошенную `IRowsetImpl::GetNextRows`.  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB требует поставщики реализуют тег **HACCESSOR**, который в массив структур **DBBINDING**.  Предоставляет **HACCESSOR** s, адреса структур **BindType**.  Обязательный в наборах строк и командах.  
  
 [IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 Делегаты в статическую функцию, определенную сопоставления столбцов поставщика.  Обязательный интерфейс в наборах строк и командах.  
  
 [IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)  
 Предоставляет сведения о доступности преобразований типов в команде или в наборе строк.  Обязательный в командах, наборов строк и наборах строк индекса.  Реализует интерфейс **IConvertType** , делегировать для преобразования, предоставленный объект OLE DB.  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 Реализует интерфейс **IDBSchemaRowset** и templatized функции `CreateSchemaRowset` создания.  
  
 [IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)  
 Открывает и возвращает набор строк, включающий все строки из одного базовой таблицы или индекса.  Обязательный интерфейс для объекта сеанса.  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 Реализует интерфейс OLE DB [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx), который позволяет обновлять значений столбцов в существующих строках, удаление строки и вставка новых строк.  
  
 [IRowsetCreatorImpl](../Topic/IRowsetCreatorImpl%20Class.md)  
 Этот класс наследуется от [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) и переопределяет [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  `IRowsetCreatorImpl` выполняет те же функции, как `IObjectWithSite`, но также содержит свойства **DBPROPCANSCROLLBACKWARDS** и **DBPROPCANFETCHBACKWARDS** OLE DB.  
  
 [IRowsetIdentityImpl](../Topic/IRowsetIdentityImpl%20Class.md)  
 Реализует интерфейс **IRowsetIdentity**, что позволяет сравнивать ли 2 строки данных или не совпадают.  
  
 [IRowsetImpl](../Topic/IRowsetImpl%20Class.md)  
 Предоставляет реализацию интерфейса `IRowset`, что базовый интерфейс набора строк.  
  
 [IRowsetInfoImpl](../Topic/IRowsetInfoImpl%20Class.md)  
 Реализует определенные свойства набора строк с помощью сопоставления набора свойств в классе команд.  Обязательный интерфейс в наборах строк.  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 Реализует интерфейс [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx), OLE DB, который обращается к произвольные строки из набора строк.  Для поддержки закладок OLE DB в наборе строк используйте набор строк наследовать от этого класса.  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 Реализует широковещательные функции для уведомления пользователей в точке подключения **IID\_IRowsetNotify** изменения содержимого набора строк.  Объект\-получатели, обрабатывающие реализуют уведомления [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) и регистрирует их в этой точке подключения.  
  
 [IRowsetUpdateImpl](../Topic/IRowsetUpdateImpl%20Class.md)  
 Реализует интерфейс OLE DB [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx), позволяющий объект\-получатели выполнять передачу изменений, сделанных с [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) к источнику данных и отменить изменения перед передачей.  
  
## Классы команд  
 [ICommandImpl](../Topic/ICommandImpl%20Class.md)  
 Предоставляет реализацию интерфейса `ICommand`.  Этот интерфейс не отображается, но обрабатывается **ICommandTextImpl**.  Обязательный интерфейс в объекте команды.  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 Эта реализация интерфейса **ICommandProperties** предусмотрена статической функцией определенной макросом `BEGIN_PROPSET_MAP`.  Обязательный в командах.  
  
 [ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)  
 Наборы, хранятся и возвращает текст команды.  Обязательный в командах.  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 Создает новую команду из объекта сеанса и возвращает запрошенный интерфейс на вновь созданной команды.  Необязательный интерфейс для объектов сеанса.  
  
 Другие классы команд `IColumnsInfoImpl` и `IAccessorImpl`, описанные в разделе классов набора строк выше.  
  
## Классы источников данных  
 [IDBInitializeImpl](../Topic/IDBInitializeImpl%20Class.md)  
 Создает и удаляет соединение с объект\-получателем.  Обязательный интерфейс для объекта источника данных и необязательные интерфейсы для перечислителей.  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` обязательный интерфейс для объектов источника данных и необязательного интерфейса для перечислителей.  Однако если перечислитель предоставляет **IDBInitialize**, он должен предоставлять `IDBProperties` \(свойства источника данных\).  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 Получает указатель интерфейса к объекту источника данных.  Обязательный интерфейс в сеансе.  
  
## Другие классы  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 Реализует свойства для различных интерфейсов свойства OLE DB \(например, `IDBProperties`, **ISessionProperties** и `IRowsetInfo`\).  
  
 [IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 Реализует интерфейс OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx), а для записи и извлечения записи из элемента данных.  
  
## См. также  
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Шаблоны OLE DB](../Topic/OLE%20DB%20Templates.md)