---
title: Архитектура шаблона поставщика OLE DB
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
ms.openlocfilehash: 89e07f95853c3611b7cceaef3f247c220c630add
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509547"
---
# <a name="ole-db-provider-template-architecture"></a>Архитектура шаблона поставщика OLE DB

## <a name="data-sources-and-sessions"></a>Источники данных и сеансы

Архитектура поставщика OLE DB включает объект источника данных и один или несколько сеансов. Объект источника данных — это начальный объект, который каждый поставщик должен создать. Когда потребительское приложение нуждается в данных, он создает объект источника данных для запуска поставщика. Объект источника данных создает объект сеанса (с помощью `IDBCreateSession` интерфейса), через который потребитель соединяется с объектом источника данных. Программисты ODBC могут считать, что объект источника данных эквивалентен `HENV` объекту и объект сеанса в качестве эквивалента `HDBC` .

![Архитектура поставщика](../../data/oledb/media/vc4twb1.gif "Архитектура поставщика")

Вместе с исходными файлами, созданными **мастером OLE DB Provider**, шаблоны OLE DB реализуют объект источника данных. Сеанс — это объект, соответствующий OLE DB `TSession` .

## <a name="mandatory-and-optional-interfaces"></a>Обязательные и необязательные интерфейсы

Шаблоны поставщика OLE DB предоставляют предупакованные реализации для всех необходимых интерфейсов. Обязательные и необязательные интерфейсы определяются OLE DB для нескольких типов объектов:

- [Источник данных](../../data/oledb/data-source-object-interfaces.md)

- [Согласованность сеанса](../../data/oledb/session-object-interfaces.md)

- [Набор строк](../../data/oledb/rowset-object-interfaces.md)

- [Команда](../../data/oledb/command-object-interfaces.md)

- [Транзакция](../../data/oledb/transaction-object-interfaces.md)

Шаблоны поставщика OLE DB не реализуют объекты Row и Storage.

В следующей таблице перечислены обязательные и необязательные интерфейсы для объектов, перечисленных выше, в соответствии с [документацией по пакету SDK для OLE DB 2,6](/previous-versions/windows/desktop/ms722784(v=vs.85)).

|Компонент|Интерфейс|Комментировать|
|---------------|---------------|-------------|
|[Источник данных](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|заполнен `IDBCreateSession`<br /><br /> заполнен `IDBInitialize`<br /><br /> заполнен `IDBProperties`<br /><br /> заполнен `IPersist`<br /><br /> используемых `IConnectionPointContainer`<br /><br /> используемых `IDBAsynchStatus`<br /><br /> используемых `IDBDataSourceAdmin`<br /><br /> используемых `IDBInfo`<br /><br /> используемых `IPersistFile`<br /><br /> используемых `ISupportErrorInfo`|Подключение от потребителя к поставщику. Объект используется для указания свойств подключения, таких как идентификатор пользователя, пароль и имя источника данных. Объект также может использоваться для администрирования источника данных (создание, обновление, удаление, таблицы и т. д.).|
|[Сеанс](../../data/oledb/session-object-interfaces.md) ([CSession](./cdataconnection-class.md#op_csession_amp))|заполнен `IGetDataSource`<br /><br /> заполнен `IOpenRowset`<br /><br /> заполнен `ISessionProperties`<br /><br /> используемых `IAlterIndex`<br /><br /> используемых `IAlterTable`<br /><br /> используемых `IBindResource`<br /><br /> используемых `ICreateRow`<br /><br /> используемых `IDBCreateCommand`<br /><br /> используемых `IDBSchemaRowset`<br /><br /> используемых `IIndexDefinition`<br /><br /> используемых `ISupportErrorInfo`<br /><br /> используемых `ITableCreation`<br /><br /> используемых `ITableDefinition`<br /><br /> используемых `ITableDefinitionWithConstraints`<br /><br /> используемых `ITransaction`<br /><br /> используемых `ITransactionJoin`<br /><br /> используемых `ITransactionLocal`<br /><br /> используемых `ITransactionObject`|Объект Session — это один диалог между потребителем и поставщиком. Он похож на ODBC `HSTMT` в том, что одновременно может быть активно несколько одновременных сеансов.<br /><br /> Объект Session — это основная ссылка для OLE DB функциональности. Чтобы перейти к команде, транзакции или объекту набора строк, выполните объект Session.|
|[Набор строк](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|заполнен `IAccessor`<br /><br /> заполнен `IColumnsInfo`<br /><br /> заполнен `IConvertType`<br /><br /> заполнен `IRowset`<br /><br /> заполнен `IRowsetInfo`<br /><br /> используемых `IChapteredRowset`<br /><br /> используемых `IColumnsInfo2`<br /><br /> используемых `IColumnsRowset`<br /><br /> используемых `IConnectionPointContainer`<br /><br /> используемых `IDBAsynchStatus`<br /><br /> используемых `IGetRow`<br /><br /> используемых `IRowsetChange`<br /><br /> используемых `IRowsetChapterMember`<br /><br /> используемых `IRowsetCurrentIndex`<br /><br /> используемых `IRowsetFind`<br /><br /> используемых `IRowsetIdentity`<br /><br /> используемых `IRowsetIndex`<br /><br /> используемых `IRowsetLocate`<br /><br /> используемых `IRowsetRefresh`<br /><br /> используемых `IRowsetScroll`<br /><br /> используемых `IRowsetUpdate`<br /><br /> используемых `IRowsetView`<br /><br /> используемых `ISupportErrorInfo`<br /><br /> используемых `IRowsetBookmark`|Объект набора строк — это данные из источника данных. Объект используется для привязок этих данных и любых основных операций (обновления, выборки, перемещения и др.) для данных. У вас всегда есть объект набора строк для сохранения данных и управления ими.|
|[Команда](../../data/oledb/command-object-interfaces.md) ([CCommand](ccommand-class.md))|заполнен `IAccessor`<br /><br /> заполнен `IColumnsInfo`<br /><br /> заполнен `ICommand`<br /><br /> заполнен `ICommandProperties`<br /><br /> заполнен `ICommandText`<br /><br /> заполнен `IConvertType`<br /><br /> используемых `IColumnsRowset`<br /><br /> используемых `ICommandPersist`<br /><br /> используемых `ICommandPrepare`<br /><br /> используемых `ICommandWithParameters`<br /><br /> используемых `ISupportErrorInfo`<br /><br /> используемых `ICommandStream`|Объект Command обрабатывает операции с данными, такими как запросы. Он может выполнять параметризованные или непараметризованные инструкции.<br /><br /> Объект Command также отвечает за обработку привязок для параметров и выходных столбцов. Привязка — это структура, которая содержит сведения о том, как должен извлекаться столбец в наборе строк. Он содержит такие сведения, как порядковый номер, тип данных, Длина и состояние.|
|[Транзакция](../../data/oledb/transaction-object-interfaces.md) (необязательно)|заполнен `IConnectionPointContainer`<br /><br /> заполнен `ITransaction`<br /><br /> используемых `ISupportErrorInfo`|Объект Transaction определяет атомарную единицу работы в источнике данных и определяет, как эти единицы работы связаны друг с другом. Этот объект не поддерживается напрямую шаблонами поставщика OLE DB (то есть создается собственный объект).|

Дополнительные сведения см. в следующих разделах:

- [Сопоставления свойств](../../data/oledb/property-maps.md)

- [Запись пользователя](../../data/oledb/user-record.md)

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Интерфейсы OLE DB](/previous-versions/windows/desktop/ms709709(v=vs.85))<br/>
