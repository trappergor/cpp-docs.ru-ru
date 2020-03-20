---
title: Ссылка на шаблоны потребителя OLE DB
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
ms.openlocfilehash: 52fe3df7e872c257aa8802f84c548ad57d21be27
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79546095"
---
# <a name="ole-db-consumer-templates-reference"></a>Ссылка на шаблоны потребителя OLE DB

Шаблоны OLE DB потребителей содержат следующие классы. Справочные материалы также содержат разделы по [макросам для OLE DB шаблонов потребителей](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

## <a name="session-classes"></a>Классы сеанса

[CDataConnection](../../data/oledb/cdataconnection-class.md)<br/>
Управляет соединением с источником данных. Это полезный класс для создания клиентов, поскольку он инкапсулирует необходимые объекты (источник данных и сеанс) и некоторую работу, которую необходимо выполнить при соединении с источником данных.

[CDataSource](../../data/oledb/cdatasource-class.md)<br/>
Соответствует объекту источника данных OLE DB, представляющему подключение через поставщик к источнику данных. Один или несколько сеансов базы данных, каждый из которых представлен объектом `CSession`, может выполняться в одном соединении.

[CEnumerator](../../data/oledb/cenumerator-class.md)<br/>
Соответствует объекту перечислителя OLE DB, который извлекает сведения о доступных источниках данных в наборе строк.

[CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)<br/>
Используется `CEnumerator` для доступа к данным из набора строк перечислителя. Этот набор строк состоит из источников данных и перечислителей, видимых из текущего перечислителя.

[CSession](../../data/oledb/csession-class.md)<br/>
Представляет отдельный сеанс доступа к базе данных. С каждым объектом `CDataSource` можно связать один или несколько сеансов.

## <a name="accessor-classes"></a>Классы методов доступа

[какцессор](../../data/oledb/caccessor-class.md)<br/>
Используется для записей, которые статически привязаны к источнику данных. Используйте этот класс метода доступа, если известна структура источника данных.

[CAccessorBase](../../data/oledb/caccessorbase-class.md)<br/>
Базовый класс для всех классов методов доступа.

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
Метод доступа, который может быть создан во время выполнения на основе сведений о столбцах набора строк. Используйте этот класс для получения данных, если структура источника данных неизвестна.

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
Метод доступа, который может использоваться при неизвестных типах команд. Получает сведения о параметрах, вызывая интерфейс `ICommandWithParameters`, если поставщик поддерживает интерфейс.

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
Позволяет получить доступ к источнику данных, когда нет сведений о базовой структуре базы данных.

[CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
Аналогично `CDynamicStringAccessor` за исключением того, что этот класс запрашивает доступ к данным из хранилища данных в виде строковых данных ANSI.

[CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
Аналогично `CDynamicStringAccessor` за исключением того, что этот класс запрашивает доступ к данным из хранилища данных в виде строковых данных в Юникоде.

[CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
Метод доступа с методами для управления как столбцами, так и параметрами команд. С помощью этого класса можно использовать любые типы данных, если поставщик может преобразовать тип.

[кноакцессор](../../data/oledb/cnoaccessor-class.md)<br/>
Может использоваться в качестве аргумента шаблона, если не требуется, чтобы класс поддерживал параметры или выходные столбцы.

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)<br/>
Аналогично `CDynamicStringAccessor` за исключением того, что этот класс преобразует все данные, доступ к которым осуществлялся из хранилища данных, в формате XML (с тегами).

## <a name="rowset-classes"></a>Классы наборов строк

[CAccessorRowset](../../data/oledb/caccessorrowset-class.md)<br/>
Инкапсулирует набор строк и связанные с ним методы доступа.

[CArrayRowset](../../data/oledb/carrayrowset-class.md)<br/>
Используется для доступа к элементам набора строк с помощью синтаксиса Array.

[CBulkRowset](../../data/oledb/cbulkrowset-class.md)<br/>
Используется для многократной выборки и управления строками путем получения нескольких дескрипторов строк с помощью одного вызова.

[кноровсет](../../data/oledb/cnorowset-class.md)<br/>
Может использоваться в качестве аргумента шаблона, если команда не возвращает набор строк.

[CRestrictions](../../data/oledb/crestrictions-class.md)<br/>
Используется для указания ограничений для наборов строк схемы.

[CRowset](../../data/oledb/crowset-class.md)<br/>
Используется для управления, установки и получения данных набора строк.

[CStreamRowset](../../data/oledb/cstreamrowset-class.md)<br/>
Возвращает `ISequentialStream` объект, а не набор строк. Затем для получения данных в формате XML используется метод `Read`. (SQL Server 2000 выполняет форматирование. Обратите внимание, что эта функция работает только с SQL Server 2000.)

[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)<br/>
Предоставляет фиктивную реализацию для `IRowsetNotify`с пустыми функциями для методов `IRowsetNotify` `OnFieldChange`, `OnRowChange`и `OnRowsetChange`.

[Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)

Шаблоны OLE DB предоставляют набор классов, соответствующих наборам строк схемы OLE DB.

## <a name="command-classes"></a>Классы команд

[CCommand](../../data/oledb/ccommand-class.md)<br/>
Используется для установки и выполнения команды OLE DB на основе параметров. Чтобы просто открыть простой набор строк, используйте вместо него `CTable`.

[CMultipleResults](../../data/oledb/cmultipleresults-class.md)<br/>
Используется в качестве аргумента шаблона для шаблона `CCommand`, если требуется, чтобы команда обрабатывала несколько результирующих наборов.

[кноакцессор](../../data/oledb/cnoaccessor-class.md)<br/>
Используется в качестве аргумента шаблона для классов шаблонов, таких как `CCommand` и `CTable`, которые принимают аргумент класса метода доступа. Используйте `CNoAccessor`, если не требуется, чтобы класс поддерживал параметры или выходные столбцы.

[CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)<br/>
Используется в качестве аргумента шаблона для шаблона `CCommand`, если требуется, чтобы команда обрабатывала один набор строк. `CNoMultipleResults` является значением по умолчанию для аргумента шаблона.

[кноровсет](../../data/oledb/cnorowset-class.md)<br/>
Используется в качестве аргумента шаблона для `CCommand` или `CTable`, если команда или таблица не возвращают набор строк.

[CTable](../../data/oledb/ctable-class.md)<br/>
Используется для доступа к простому набору строк без параметров.

## <a name="property-classes"></a>Классы свойств

[кдбпропидсет](../../data/oledb/cdbpropidset-class.md)<br/>
Используется для передачи массива идентификаторов свойств, для которых потребитель хочет получить сведения о свойствах. Свойства принадлежат одному набору свойств.

[кдбпропсет](../../data/oledb/cdbpropset-class.md)<br/>
Используется для задания свойств поставщика.

## <a name="bookmark-class"></a>Bookmark, класс

[CBookmark](../../data/oledb/cbookmark-class.md)<br/>
Используется в качестве индекса для доступа к данным в наборе строк.

## <a name="error-class"></a>Класс Error

[CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)<br/>
Используется для получения сведений об ошибках OLE DB.

## <a name="see-also"></a>См. также:

[Ссылка на шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[Шаблоны OLE DB](../../data/oledb/ole-db-templates.md)