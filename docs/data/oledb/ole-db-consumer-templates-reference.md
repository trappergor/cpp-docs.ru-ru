---
title: "Ссылка на шаблоны потребителя OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-attr.db_param"
  - "vc-attr.db_column"
  - "vc-attr.db_accessor"
  - "vc-attr.db_command"
  - "vc-attr.db_table"
  - "vc.templates.ole"
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "шаблоны потребителя OLE DB, классы"
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Ссылка на шаблоны потребителя OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Шаблоны объект\-получателя OLE DB содержит следующие классы.  Опорный материал также разделы в [макросы для шаблонов объект\-получателя OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md).  
  
## Классы сеанса  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 Управление соединение с источником данных.  Это полезный класс для создания клиентов, поскольку он инкапсулирует необходимые объекты \(источник данных\) и сеанс и часть работы необходимо сделать при подключении к источнику данных.  
  
 [CDataSource](../Topic/CDataSource%20Class.md)  
 Соответствует объекту источника данных OLE DB, указание подключение с помощью поставщика к источнику данных.  Один или несколько сеансов базы данных, каждый из которых представлен объектом `CSession`, могут выполняться на одном соединении.  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 Соответствует объекту перечислителя OLE DB, который извлекает данные набора строк о доступных источниках данных.  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 Используется `CEnumerator` для получения данных из набора строк перечислителя.  Этот набор строк содержит источников данных и для перечислителей из текущего перечислителя.  
  
 [CSession](../../data/oledb/csession-class.md)  
 Представляет один сеанс доступа к базе данных.  Один или несколько сеансов можно связать с каждым объектом `CDataSource`.  
  
## Классы методов доступа  
 [CAccessor](../Topic/CAccessor%20Class.md)  
 Используется для записей, которые статически привязаны к источнику данных.  Этот класс доступа, если известны структуру источника данных.  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 Базовый класс для всех классов доступа.  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 Доступ, можно создать во время выполнения на основе информации о столбцах набора строк.  Этот класс используется для извлечения данных неизвестен, если структура источника данных.  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 Доступ, который можно использовать при неизвестных типов команд.  Получает сведения о параметрах путем вызова интерфейса `ICommandWithParameters`, если поставщик поддерживает интерфейс.  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 Позволяет получить доступ к источнику данных в случае, если отсутствует информация о базовая структура.  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 Аналогично `CDynamicStringAccessor` за исключением того, что эти данные запросов класса параллельного доступа из хранилища данных в виде строковых данных ANSI.  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 Аналогично `CDynamicStringAccessor` за исключением того, что эти данные запросов класса параллельного доступа из хранилища данных в качестве данных строки юникода.  
  
 [CManualAccessor](../Topic/CManualAccessor%20Class.md)  
 Доступ с методами для обработки и столбцы и параметры команд.  С этим классом, можно использовать типы любых данных, если поставщик может преобразовать тип.  
  
 [CNoAccessor](../Topic/CNoAccessor%20Class.md)  
 Может использоваться в качестве аргумента шаблона при необходимости класс поддержки параметров и выходные столбцы.  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 Аналогично `CDynamicStringAccessor` за исключением того, что данный класс преобразует все данные, получаемые доступ из хранилища данных, что представляют собой \(помеченные тегами\) данные.  
  
## Классы набора строк  
 [CAccessorRowset](../Topic/CAccessorRowset%20Class.md)  
 Инкапсулирует набор строк и связанные методы доступа.  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 Используется для доступа к элементам набора строк с помощью синтаксиса массива.  
  
 [CBulkRowset](../Topic/CBulkRowset%20Class.md)  
 Используется для получения и работы со строками в пакетной путем получения нескольких строк с одним вызовом.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Может использоваться в качестве аргумента шаблона, если команда не возвращает набор строк.  
  
 [CRestrictions](../Topic/CRestrictions%20Class.md)  
 Задает ограничения для наборов строк схемы.  
  
 [CRowset](../Topic/CRowset%20Class.md)  
 Используется для управления, задавать и извлечь данные набора строк.  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 Возвращает объект `ISequentialStream` вместо набор строк; затем используется метод **Чтение**, чтобы получить данные в формате XML. \(SQL Server 2000 выполняет форматирование; обратите внимание, что эта функция работает только с SQL Server 2000\).  
  
 [IRowsetNotifyImpl](../Topic/IRowsetNotifyImpl%20Class.md)  
 Предоставляет фиктивную реализацию `IRowsetNotify`, с пустыми функциями для методов `OnFieldChange`, `OnRowChange` и `OnRowsetChange``IRowsetNotify`.  
  
 [Классы набора строк схемы и классах typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)  
  
 Шаблоны OLE DB предоставляют возможность набором классов, соответствующие наборы строк схемы OLE DB.  
  
## Классы команд  
 [CCommand](../../data/oledb/ccommand-class.md)  
 Используется для задания и выполнения команды параметр\- на основе OLE DB.  Просто для открытия простой набор строк, используйте вместо этого `CTable`  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 Используется в качестве аргумента шаблона для шаблона `CCommand` при необходимости команду обрабатывать несколько результирующих наборов.  
  
 [CNoAccessor](../Topic/CNoAccessor%20Class.md)  
 Используется в качестве аргумента шаблона для шаблонных классов, например `CCommand` и `CTable`, которые принимают аргумент класса доступа.  Используйте `CNoAccessor`, если не требуется поддерживать класс параметров и выходные столбцы.  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 Используется в качестве аргумента шаблона для шаблона `CCommand` при необходимости команды обработки один набор строк.  `CNoMultipleResults` значение по умолчанию для аргумента шаблона.  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 Используется в качестве аргумента шаблона для `CCommand` или `CTable`, если команда или таблица не возвращают набор строк.  
  
 [CTable](../../data/oledb/ctable-class.md)  
 Используется для получения простого набора строк без параметров.  
  
## Классы свойства  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 Используется для передачи массив идентификаторов свойства, для которых требуется объект\-получатель данные свойства.  Свойства принадлежат одному набор свойств.  
  
 [CDBPropSet](../Topic/CDBPropSet%20Class.md)  
 Используется для указания свойства от поставщика.  
  
## Класс Bookmark  
 [CBookmark](../../data/oledb/cbookmark-class.md)  
 Используется в качестве индекса для доступа к данным в наборе строк.  
  
## Класс Error  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 Используется для получения сведений об ошибке OLE DB.  
  
## См. также  
 [Ссылка на шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)   
 [Шаблоны OLE DB](../Topic/OLE%20DB%20Templates.md)