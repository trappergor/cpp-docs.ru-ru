---
title: Ссылка на шаблоны OLE DB потребителей | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc.templates.ole
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a1aed8d2e00631ccd02a7ef3a966b8fd8a279938
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068116"
---
# <a name="ole-db-consumer-templates-reference"></a>Ссылка на шаблоны потребителя OLE DB

Шаблоны потребителей OLE DB содержит следующие классы. Справочные материалы также разделы на [макросы для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

## <a name="session-classes"></a>Классы сеансов

[CDataConnection](../../data/oledb/cdataconnection-class.md)<br/>
Управляет соединением с источником данных. Это полезно класс для создания клиентов, так как он инкапсулирует необходимых объектов (источника данных и сеанса) и некоторых операций, которые необходимо выполнить при подключении к источнику данных.

[CDataSource](../../data/oledb/cdatasource-class.md)<br/>
Соответствующий объект источника данных OLE DB, представляющий подключение через поставщика к источнику данных. Один или несколько сеансов базы данных, каждый из которых представлен `CSession` объекта, могут выполняться в одном соединении.

[CEnumerator](../../data/oledb/cenumerator-class.md)<br/>
Соответствующий объект перечисления OLE DB, который извлекает сведения о наборе строк о доступных источниках данных.

[CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)<br/>
Используемые `CEnumerator` доступ к данным из перечислитель набора строк. Этот набор строк состоит из источников данных и перечислители, отображается в текущий перечислитель.

[CSession](../../data/oledb/csession-class.md)<br/>
Представляет сеанс доступа к отдельной базы данных. Один или несколько сеансов можно связать с каждым `CDataSource` объекта.

## <a name="accessor-classes"></a>Классы методов доступа

[CAccessor](../../data/oledb/caccessor-class.md)<br/>
Используется для записи, которые статически привязаны к источнику данных. Используйте этот класс метода доступа, если вы знаете структуру источника данных.

[CAccessorBase](../../data/oledb/caccessorbase-class.md)<br/>
Базовый класс для всех классов метода доступа.

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
Метод доступа, которые могут быть созданы во время выполнения на основе данных столбца набора строк. Этот класс используется для получения данных, если вы не знаете структуру источника данных.

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
Метод доступа, который может использоваться, когда неизвестны типы команд. Получает сведения о параметрах путем вызова `ICommandWithParameters` интерфейс, если поставщик поддерживает интерфейс.

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
Предоставляет возможность доступа к источнику данных, если вы не имеют сведений о базовой структуры базы данных.

[CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
Аналогичную `CDynamicStringAccessor` за исключением того, что этот класс запрашивает данные из хранилища данных в виде строковых данных ANSI.

[CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
Аналогичную `CDynamicStringAccessor` за исключением того, что этот класс запрашивает данные из хранилища данных в виде строки в Юникоде.

[CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
Метод доступа с помощью методов для обработки столбцов и параметров команды. С этим классом можно использовать любые типы данных до тех пор, пока поставщик может преобразовать тип.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
Можно использовать как аргумент шаблона при нежелательно класс для поддержки параметров или выходные столбцы.

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)<br/>
Аналогичную `CDynamicStringAccessor` за исключением того, что этот класс преобразует все данные из хранилища данных в виде XML-данных (с тегами).

## <a name="rowset-classes"></a>Классы набора строк

[CAccessorRowset](../../data/oledb/caccessorrowset-class.md)<br/>
Инкапсулирует набор строк и его связанные методы доступа.

[CArrayRowset](../../data/oledb/carrayrowset-class.md)<br/>
Используется для доступа к элементам набора строк с помощью синтаксиса массива.

[CBulkRowset](../../data/oledb/cbulkrowset-class.md)<br/>
Используется для получения и изменения строк в пакетном режиме путем получения несколько дескрипторов строк с помощью одного вызова.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
Можно использовать как аргумент шаблона, если команда не возвращает набор строк.

[cRestrictions](../../data/oledb/crestrictions-class.md)<br/>
Используется для указания ограничения для наборов строк схемы.

[CRowset](../../data/oledb/crowset-class.md)<br/>
Используется для управления, задание и получение данных набора строк.

[CStreamRowset](../../data/oledb/cstreamrowset-class.md)<br/>
Возвращает `ISequentialStream` объекта вместо набора строк; затем использовать `Read` метод для извлечения данных в формате XML. (SQL Server 2000 не форматирование, обратите внимание на то, что эта функция работает с SQL Server 2000 только).

[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)<br/>
Предоставляет реализацию для фиктивного `IRowsetNotify`, с пустым функциями для `IRowsetNotify` методы `OnFieldChange`, `OnRowChange`, и `OnRowsetChange`.

[Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)

Шаблоны OLE DB предоставляют набор классов, соответствующие наборы строк схемы OLE DB.

## <a name="command-classes"></a>Классы команд

[CCommand](../../data/oledb/ccommand-class.md)<br/>
Используется для задания и выполнения параметризованные команды OLE DB. Чтобы просто открыть простого набора строк, используйте `CTable` вместо этого.

[CMultipleResults](../../data/oledb/cmultipleresults-class.md)<br/>
Используется в качестве аргумента шаблона для `CCommand` шаблон команды для обработки нескольких результирующих наборов.

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
Использовать в качестве аргумента шаблона для шаблона классов, таких как `CCommand` и `CTable`, которые принимают аргумент метода доступа класса. Используйте `CNoAccessor` Если не хотите, чтобы класс для поддержки параметров или выходные столбцы.

[CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)<br/>
Используется в качестве аргумента шаблона для `CCommand` шаблон команду, чтобы обрабатывать один набор строк. `CNoMultipleResults` значение по умолчанию для аргумента шаблона.

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
Используется в качестве аргумента шаблона для `CCommand` или `CTable` Если команд или таблиц не возвращает набор строк.

[CTable](../../data/oledb/ctable-class.md)<br/>
Используется для простого набора строк без параметров.

## <a name="property-classes"></a>Классы свойств

[CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)<br/>
Используется для передачи массив идентификаторов свойств, для которых потребителю нужны сведения о свойстве. Свойства принадлежат набору одно свойство.

[CDBPropSet](../../data/oledb/cdbpropset-class.md)<br/>
Используется для задания свойств в поставщике.

## <a name="bookmark-class"></a>Класс закладки

[CBookmark](../../data/oledb/cbookmark-class.md)<br/>
Использовать как индекс для доступа к данным в наборе строк.

## <a name="error-class"></a>Класс ошибки

[CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)<br/>
Используется для получения сведений об ошибке OLE DB.

## <a name="see-also"></a>См. также

[Ссылка на шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Шаблоны OLE DB](../../data/oledb/ole-db-templates.md)