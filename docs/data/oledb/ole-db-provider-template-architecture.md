---
title: "Архитектура шаблона поставщика OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "архитектура [C++], поставщик OLE DB"
  - "OLE DB [C++], объектная модель"
  - "шаблоны поставщика OLE DB, объектная модель"
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Архитектура шаблона поставщика OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Источники данных и сеансы  
 Архитектура поставщика OLE DB включает объект источника данных, а также один или несколько сеансов.  Объект источника данных является первым объектом, который должен создавать любой поставщик.  Когда приложению\-потребителю требуются данные, оно совместно создает объект источника данных для запуска поставщика.  Объект источника данных создает объект сеанса \(используя интерфейс **IDBCreateSession**\), с помощью которого потребитель подключается к объекту источника данных.  Программисты ODBC могут представлять себе объект источника данных как эквивалент **HENV**, а объект сеанса — как эквивалент **HDBC**.  
  
 ![Архитектура поставщика](../../data/oledb/media/vc4twb1.gif "vc4TWB1")  
  
 Вместе с исходными файлами, созданными мастером поставщиков OLE DB, шаблоны OLE DB реализуют объект источника данных.  Сеанс — это объект, соответствующий объекту OLE DB **TSession**.  
  
## Обязательные и необязательные интерфейсы  
 Шаблоны поставщика OLE DB обеспечивают предварительно упакованные реализации для всех необходимых интерфейсов.  В OLE DB обязательные и необязательные интерфейсы определяются для нескольких типов объектов:  
  
-   [Источник данных](../../data/oledb/data-source-object-interfaces.md)  
  
-   [Сеанс;](../../data/oledb/session-object-interfaces.md)  
  
-   [Набор строк;](../Topic/Rowset%20Object%20Interfaces.md)  
  
-   [Команда](../../data/oledb/command-object-interfaces.md)  
  
-   [Транзакция](../../data/oledb/transaction-object-interfaces.md)  
  
 Обратите внимание, что шаблоны поставщика OLE DB не реализуют объекты строк и хранилищ.  
  
 В следующей таблице в соответствии с [Документацией для пакета SDK OLE DB 2.6](https://msdn.microsoft.com/en-us/library/ms722784.aspx) перечислены обязательные и необязательные интерфейсы для вышеперечисленных объектов.  
  
|Компонент|Интерфейс|Комментарий|  
|---------------|---------------|-----------------|  
|[Источник данных](../../data/oledb/data-source-object-interfaces.md) \([CDataSource](../Topic/CDataSource%20Class.md)\)|\(обязательный\) **IDBCreateSession**<br /><br /> \(обязательный\) **IDBInitialize**<br /><br /> \(обязательный\) `IDBProperties`<br /><br /> \(обязательный\) `IPersist`<br /><br /> \(необязательный\) **IConnectionPointContainer**<br /><br /> \(необязательный\) **IDBAsynchStatus**<br /><br /> \(необязательный\) **IDBDataSourceAdmin**<br /><br /> \(необязательный\) **IDBInfo**<br /><br /> \(необязательный\) `IPersistFile`<br /><br /> \(необязательный\) **ISupportErrorInfo**|Подключение от потребителя к поставщику.  Объект используется для указания свойств подключения, например, идентификатора пользователя, пароля и имени источника данных.  Объект также может использоваться для администрирования источника данных \(создания, обновления, удаления таблиц и т.п.\).|  
|[Сеанс](../../data/oledb/session-object-interfaces.md) \([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md)\)|\(обязательный\) **IGetDataSource**<br /><br /> \(обязательный\) `IOpenRowset`<br /><br /> \(обязательный\) **ISessionProperties**<br /><br /> \(необязательный\) **IAlterIndex**<br /><br /> \(необязательный\) **IAlterTable**<br /><br /> \(необязательный\) **IBindResource**<br /><br /> \(необязательный\) **ICreateRow**<br /><br /> \(необязательный\) **IDBCreateCommand**<br /><br /> \(необязательный\) **IDBSchemaRowset**<br /><br /> \(необязательный\) **IIndexDefinition**<br /><br /> \(необязательный\) **ISupportErrorInfo**<br /><br /> \(необязательный\) **ITableCreation**<br /><br /> \(необязательный\) **ITableDefinition**<br /><br /> \(необязательный\) **ITableDefinitionWithConstraints**<br /><br /> \(необязательный\) **ITransaction**<br /><br /> \(необязательный\) **ITransactionJoin**<br /><br /> \(необязательный\) **ITransactionLocal**<br /><br /> \(необязательный\) **ITransactionObject**|Объект сеанса представляет собой одиночный экземпляр диалога между потребителем и поставщиком.  Поведение этого класса в чем\-то похоже на поведение типа ODBC **HSTMT** тем, что в определенный момент времени может быть активно несколько сеансов.<br /><br /> Объект сеанса является основной ссылкой для использования функциональности OLE DB.  Объект сеанса необходим для получения объектов команд, транзакций и наборов строк.|  
|[Набор строк](../Topic/Rowset%20Object%20Interfaces.md) \([CRowset](../Topic/CRowset%20Class.md)\)|\(обязательный\) `IAccessor`<br /><br /> \(обязательный\) `IColumnsInfo`<br /><br /> \(обязательный\) **IConvertType**<br /><br /> \(обязательный\) `IRowset`<br /><br /> \(обязательный\) `IRowsetInfo`<br /><br /> \(необязательный\) **IChapteredRowset**<br /><br /> \(необязательный\) **IColumnsInfo2**<br /><br /> \(необязательный\) **IColumnsRowset**<br /><br /> \(необязательный\) **IConnectionPointContainer**<br /><br /> \(необязательный\) **IDBAsynchStatus**<br /><br /> \(необязательный\) **IGetRow**<br /><br /> \(необязательный\) `IRowsetChange`<br /><br /> \(необязательный\) **IRowsetChapterMember**<br /><br /> \(необязательный\) **IRowsetCurrentIndex**<br /><br /> \(необязательный\) **IRowsetFind**<br /><br /> \(необязательный\) **IRowsetIdentity**<br /><br /> \(необязательный\) **IRowsetIndex**<br /><br /> \(необязательный\) `IRowsetLocate`<br /><br /> \(необязательный\) **IRowsetRefresh**<br /><br /> \(необязательный\) `IRowsetScroll`<br /><br /> \(необязательный\) `IRowsetUpdate`<br /><br /> \(необязательный\) **IRowsetView**<br /><br /> \(необязательный\) **ISupportErrorInfo**<br /><br /> \(необязательный\) **IRowsetBookmark**|Объект набора строк служит для представления данных из источника данных.  Объект отвечает за привязку этих данных и все базовые операции с этими данными \(обновление, выборку, перемещение и др.\).  Для хранения данных и управления ими всегда используется объект набора строк.|  
|[Команда](../../data/oledb/command-object-interfaces.md) \([CCommand](http://msdn.microsoft.com/ru-ru/52bef5da-c1a0-4223-b4e6-9e464b6db409)\)|\(обязательный\) `IAccessor`<br /><br /> \(обязательный\) `IColumnsInfo`<br /><br /> \(обязательный\) `ICommand`<br /><br /> \(обязательный\) **ICommandProperties**<br /><br /> \(обязательный\) `ICommandText`<br /><br /> \(обязательный\) **IConvertType**<br /><br /> \(необязательный\) **IColumnsRowset**<br /><br /> \(необязательный\) **ICommandPersist**<br /><br /> \(необязательный\) **ICommandPrepare**<br /><br /> \(необязательный\) `ICommandWithParameters`<br /><br /> \(необязательный\) **ISupportErrorInfo**<br /><br /> \(необязательный\) **ICommandStream**|Объект команды обрабатывает операции с данными, например запросы.  Он может обрабатывать параметризованные или непараметризованные инструкции.<br /><br /> Объект команды также отвечает за обработку привязки параметров и выходных столбцов.  Привязка представляет собой структуру, содержащую информацию об извлечении столбца из набора строк.  Она содержит такую информацию, как порядковый номер, тип данных, длина и состояние.|  
|[Транзакция](../../data/oledb/transaction-object-interfaces.md) \(необязательный\)|\(обязательный\) **IConnectionPointContainer**<br /><br /> \(обязательный\) **ITransaction**<br /><br /> \(необязательный\) **ISupportErrorInfo**|Объект транзакции определяет неделимую единицу работы в источнике данных и отношения этих единиц друг к другу.  Этот объект не поддерживается напрямую шаблонами поставщика OLE DB \(т.е. пользователь создает свой собственный объект\).|  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Сопоставления свойств](../../data/oledb/property-maps.md)  
  
-   [Запись пользователя](../../data/oledb/user-record.md)  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Interfaces](https://msdn.microsoft.com/en-us/library/ms709709.aspx)