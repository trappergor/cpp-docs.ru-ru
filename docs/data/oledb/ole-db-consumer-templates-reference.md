---
title: Ссылка на шаблоны потребителя OLE DB | Документы Microsoft
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
ms.openlocfilehash: b5b599a1c7a1b256cc9c56d772a15621beda286f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112060"
---
# <a name="ole-db-consumer-templates-reference"></a>Ссылка на шаблоны потребителя OLE DB
Шаблоны потребителей OLE DB содержит следующие классы. Справочные материалы также содержатся разделы о [макросы для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## <a name="session-classes"></a>Классы сеансов  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 Управляет соединение с источником данных. Это класс особенно полезен для создания клиентов, так как он инкапсулирует необходимых объектов (источника данных и сеанса) и некоторых операций, которые необходимо выполнить при подключении к источнику данных.  
  
 [CDataSource](../../data/oledb/cdatasource-class.md)  
 Соответствующий объект источника данных OLE DB, представляющий подключение через поставщика для источника данных. Один или несколько сеансов базы данных, каждый из которых представлен `CSession` объекта, могут выполняться в одном соединении.  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 Соответствующий объект перечисления OLE DB, который извлекает набор строк информации о доступных источниках данных.  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 Используемые `CEnumerator` доступ к данным из перечислитель набора строк. Этот набор строк состоит из источников данных и перечислителей, видимый из текущего перечислителя.  
  
 [CSession](../../data/oledb/csession-class.md)  
 Представляет сеанс доступа к одной базе данных. Один или несколько сеансов можно связать с каждым `CDataSource` объекта.  
  
## <a name="accessor-classes"></a>Классы методов доступа  
 [CAccessor](../../data/oledb/caccessor-class.md)  
 Используется для записи, которые статически привязаны к источнику данных. Используйте этот класс метода доступа, если известно структуру источника данных.  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 Базовый класс для всех классов метода доступа.  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 Метод доступа, которые могут быть созданы во время выполнения на основе данных столбца набора строк. Этот класс используется для получения данных, если вы не знаете структуру источника данных.  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 Метод доступа, который может использоваться, когда неизвестны типы команд. Получает сведения о параметрах путем вызова метода `ICommandWithParameters` интерфейс, если поставщик поддерживает интерфейс.  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 Дает возможность доступа к источнику данных, если у вас нет сведений о базовой структуры базы данных.  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 Аналогично `CDynamicStringAccessor` за исключением того, что этот класс запрашивает данные из хранилища данных в виде строковых данных ANSI.  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 Аналогично `CDynamicStringAccessor` за исключением того, что этот класс запрашивает данные из хранилища данных в виде строки в Юникоде.  
  
 [CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  
 Метод доступа с помощью методов для обработки столбцов и параметров команды. С помощью этого класса можно использовать типы данных, при условии, что поставщик может преобразовать типы.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Может использоваться как аргумент шаблона, когда требуется класс для поддержки параметров или выходные столбцы.  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 Аналогично `CDynamicStringAccessor` за исключением того, что этот класс преобразует все данные из хранилища данных в виде XML-данных (с тегом).  
  
## <a name="rowset-classes"></a>Классы набора строк  
 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)  
 Инкапсулирует набор строк и его связанные методы доступа.  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 Используется для доступа к элементам набора строк, используя синтаксис массива.  
  
 [CBulkRowset](../../data/oledb/cbulkrowset-class.md)  
 Используется для извлечения, а также операций со строками в большом количестве путем извлечения нескольких дескрипторов строк с помощью одного вызова.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Может использоваться как аргумент шаблона, если команда не возвращает набор строк.  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md)  
 Можно задать ограничения для наборов строк схемы.  
  
 [CRowset](../../data/oledb/crowset-class.md)  
 Используется для управления и извлечения набора строк данных.  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 Возвращает `ISequentialStream` объекта вместо набора строк; затем использовать **чтения** метод для извлечения данных в формате XML. (SQL Server 2000 не форматирование, обратите внимание, что эта функция работает с SQL Server 2000 только).  
  
 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)  
 Предоставляет реализацию фиктивный `IRowsetNotify`, с пустым функции для `IRowsetNotify` методы `OnFieldChange`, `OnRowChange`, и `OnRowsetChange`.  
  
 [Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)  
  
 Шаблоны OLE DB предоставляют набор классов, которые соответствуют наборы строк схемы OLE DB.  
  
## <a name="command-classes"></a>Командные классы  
 [CCommand](../../data/oledb/ccommand-class.md)  
 Используется для задания и выполнения команды на основе параметра OLE DB. Чтобы просто открыть простого набора строк, используйте `CTable` вместо него.  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 Используется в качестве аргумента шаблона для `CCommand` шаблон при необходимости команды для обработки нескольких результирующих наборов.  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 Использовать в качестве аргумента шаблона для шаблона классов, таких как `CCommand` и `CTable`, которые принимают аргумент класса метода доступа. Используйте `CNoAccessor` не выполнять класс для поддержки параметров или выходные столбцы.  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 Используется в качестве аргумента шаблона для `CCommand` шаблон при необходимости команды для обработки один набор строк. `CNoMultipleResults` значение по умолчанию для аргумента шаблона.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Используется в качестве аргумента шаблона для `CCommand` или `CTable` Если команд или таблиц не возвращает набор строк.  
  
 [CTable](../../data/oledb/ctable-class.md)  
 Используется для простого набора строк без параметров.  
  
## <a name="property-classes"></a>Классы свойств  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 Используется для передачи массив идентификаторов свойств, для которых потребителю нужны сведения о свойстве. Свойства принадлежат набору одно свойство.  
  
 [CDBPropSet](../../data/oledb/cdbpropset-class.md)  
 Используется для задания свойств в поставщике.  
  
## <a name="bookmark-class"></a>Bookmark-класс  
 [CBookmark](../../data/oledb/cbookmark-class.md)  
 Использовать в качестве индекса для доступа к данным в наборе строк.  
  
## <a name="error-class"></a>Ошибка-класс  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 Используется для получения сведений об ошибке OLE DB.  
  
## <a name="see-also"></a>См. также  
 [Ссылка на шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)   
 [Шаблоны OLE DB](../../data/oledb/ole-db-templates.md)