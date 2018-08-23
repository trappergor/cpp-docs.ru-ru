---
title: Архитектура шаблона поставщика OLE DB | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e4170e2089cbfc584c5832e4a1a0542f360741c5
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572513"
---
# <a name="ole-db-provider-template-architecture"></a>Архитектура шаблона поставщика OLE DB
## <a name="data-sources-and-sessions"></a>Источники данных и сеансы  
 Архитектура поставщика OLE DB включает объект источника данных и один или несколько сеансов. Объект источника данных является первым объектом, который должен создавать любой поставщик. Когда приложение-потребитель данных, совместно создает объект источника данных для запуска поставщика. Объект источника данных создает объект сеанса (с помощью `IDBCreateSession` интерфейс) через потребитель подключается к объекту источника данных. Программисты ODBC могут представлять объект источника данных как эквивалент `HENV` и объект сеанса как эквивалент `HDBC`.  
  
 ![Архитектура поставщика](../../data/oledb/media/vc4twb1.gif "vc4twb1")  
  
 Вместе с исходными файлами, созданными с помощью мастера поставщика OLE DB шаблоны OLE DB реализуют объект источника данных. Сеанс — это объект, который соответствует OLE DB `TSession`.  
  
## <a name="mandatory-and-optional-interfaces"></a>Обязательные и необязательные интерфейсы  
 Шаблоны поставщика OLE DB предоставляют упакованные реализации для всех требуемых интерфейсов. Обязательные и необязательные интерфейсы определяются в OLE DB для нескольких типов объектов:  
  
-   [Источник данных](../../data/oledb/data-source-object-interfaces.md)  
  
-   [Сеанс](../../data/oledb/session-object-interfaces.md)  
  
-   [Набор строк](../../data/oledb/rowset-object-interfaces.md)  
  
-   [Команда](../../data/oledb/command-object-interfaces.md)  
  
-   [Транзакция](../../data/oledb/transaction-object-interfaces.md)  
  
 Обратите внимание, что шаблоны поставщика OLE DB не реализуют объекты строк и хранилищ.  
  
 В следующей таблице перечислены обязательные и необязательные интерфейсы для объектов, перечисленных выше, согласно [OLE DB версии 2.6 документации по пакету SDK](/previous-versions/windows/desktop/ms722784\(v=vs.85\)).  
  
|Компонент|Интерфейс|Комментарий|  
|---------------|---------------|-------------|  
|[Источник данных](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|[обязательный] `IDBCreateSession`<br /><br /> [обязательный] `IDBInitialize`<br /><br /> [обязательный] `IDBProperties`<br /><br /> [обязательный] `IPersist`<br /><br /> [необязательно] `IConnectionPointContainer`<br /><br /> [необязательно] `IDBAsynchStatus`<br /><br /> [необязательно] `IDBDataSourceAdmin`<br /><br /> [необязательно] `IDBInfo`<br /><br /> [необязательно] `IPersistFile`<br /><br /> [необязательно] `ISupportErrorInfo`|Подключение от потребителя к поставщику. Объект используется для указания свойств подключения, например имя пользователя, идентификатор, пароль и данные источника. Объект также может использоваться для администрирования источника данных (создавать, обновлять, удалять, таблиц и так далее).|  
|[Сеанс](../../data/oledb/session-object-interfaces.md) ([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[обязательный] `IGetDataSource`<br /><br /> [обязательный] `IOpenRowset`<br /><br /> [обязательный] `ISessionProperties`<br /><br /> [необязательно] `IAlterIndex`<br /><br /> [необязательно] `IAlterTable`<br /><br /> [необязательно] `IBindResource`<br /><br /> [необязательно] `ICreateRow`<br /><br /> [необязательно] `IDBCreateCommand`<br /><br /> [необязательно] `IDBSchemaRowset`<br /><br /> [необязательно] `IIndexDefinition`<br /><br /> [необязательно] `ISupportErrorInfo`<br /><br /> [необязательно] `ITableCreation`<br /><br /> [необязательно] `ITableDefinition`<br /><br /> [необязательно] `ITableDefinitionWithConstraints`<br /><br /> [необязательно] `ITransaction`<br /><br /> [необязательно] `ITransactionJoin`<br /><br /> [необязательно] `ITransactionLocal`<br /><br /> [необязательно] `ITransactionObject`|Объект сеанса представляет один диалог между потребителем и поставщиком. Это отчасти похоже на ODBC `HSTMT` тем, что может существовать несколько сеансов active.<br /><br /> Объект сеанса является основной ссылкой для получения функциональности OLE DB. Чтобы открыть команды, транзакций или объекта набора строк, проходят объект сеанса.|  
|[Набор строк](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|[обязательный] `IAccessor`<br /><br /> [обязательный] `IColumnsInfo`<br /><br /> [обязательный] `IConvertType`<br /><br /> [обязательный] `IRowset`<br /><br /> [обязательный] `IRowsetInfo`<br /><br /> [необязательно] `IChapteredRowset`<br /><br /> [необязательно] `IColumnsInfo2`<br /><br /> [необязательно] `IColumnsRowset`<br /><br /> [необязательно] `IConnectionPointContainer`<br /><br /> [необязательно] `IDBAsynchStatus`<br /><br /> [необязательно] `IGetRow`<br /><br /> [необязательно] `IRowsetChange`<br /><br /> [необязательно] `IRowsetChapterMember`<br /><br /> [необязательно] `IRowsetCurrentIndex`<br /><br /> [необязательно] `IRowsetFind`<br /><br /> [необязательно] `IRowsetIdentity`<br /><br /> [необязательно] `IRowsetIndex`<br /><br /> [необязательно] `IRowsetLocate`<br /><br /> [необязательно] `IRowsetRefresh`<br /><br /> [необязательно] `IRowsetScroll`<br /><br /> [необязательно] `IRowsetUpdate`<br /><br /> [необязательно] `IRowsetView`<br /><br /> [необязательно] `ISupportErrorInfo`<br /><br /> [необязательно] `IRowsetBookmark`|Объект набора строк представляет данные из источника данных. Объект несет ответственность за привязок данных и все базовые операции (обновления, выборки, перемещения и другие) данных. У вас всегда есть объект набора строк, содержащих и обрабатывать.|  
|[Команда](../../data/oledb/command-object-interfaces.md) ([CCommand](http://msdn.microsoft.com/52bef5da-c1a0-4223-b4e6-9e464b6db409))|[обязательный] `IAccessor`<br /><br /> [обязательный] `IColumnsInfo`<br /><br /> [обязательный] `ICommand`<br /><br /> [обязательный] `ICommandProperties`<br /><br /> [обязательный] `ICommandText`<br /><br /> [обязательный] `IConvertType`<br /><br /> [необязательно] `IColumnsRowset`<br /><br /> [необязательно] `ICommandPersist`<br /><br /> [необязательно] `ICommandPrepare`<br /><br /> [необязательно] `ICommandWithParameters`<br /><br /> [необязательно] `ISupportErrorInfo`<br /><br /> [необязательно] `ICommandStream`|Объект команды обрабатывает операции с данными, например запросы. Он может обрабатывать инструкции параметризованных или без параметров.<br /><br /> Объект команды также отвечает за обработку привязки параметров и выходных столбцов. Привязка имеет структуру, содержащую сведения о том, как столбец, в наборе строк должны быть получены. Он содержит сведения, такие как порядковый номер, тип данных, длина и состояние.|  
|[Транзакции](../../data/oledb/transaction-object-interfaces.md) (необязательно)|[обязательный] `IConnectionPointContainer`<br /><br /> [обязательный] `ITransaction`<br /><br /> [необязательно] `ISupportErrorInfo`|Объект транзакции определяет атомарной единицей работы над источником данных и определяет, каким образом эти единицы работы связаны друг с другом. Этот объект не поддерживается напрямую с помощью шаблонов поставщика OLE DB (то есть создать собственный объект).|  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Сопоставления свойств](../../data/oledb/property-maps.md)  
  
-   [Записи пользователя](../../data/oledb/user-record.md)  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Интерфейсы OLE DB](/previous-versions/windows/desktop/ms709709\(v=vs.85\))