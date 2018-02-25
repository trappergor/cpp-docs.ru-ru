---
title: "Команды и таблицы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, table support
- CCommand class, OLE DB consumer templates
- commands [C++], OLE DB Consumer Templates
- CTable class
- CAccessorRowset class, command and table classes
- rowsets, accessing
- tables [C++], OLE DB Consumer Templates
- OLE DB consumer templates, command support
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3500b5b39e4f6e483789cdc13a055b2fe45fa39
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="commands-and-tables"></a>Команды и таблицы
Команды и таблицы позволяют получить доступ к наборы строк; т. е откройте наборы строк, выполнять команды и привяжите столбцы. [CCommand](../../data/oledb/ccommand-class.md) и [CTable](../../data/oledb/ctable-class.md) классов, создания экземпляров объектов команд и таблиц, соответственно. Эти классы являются производными от [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) как показано на следующем рисунке.  
  
 ![CCommand и CTable](../../data/oledb/media/vccommandstables.gif "vccommandstables")  
Классы команд и таблиц  
  
 В таблице выше `TAccessor` может быть любым типом метода доступа, перечисленных в [типы методов доступа](../../data/oledb/accessors-and-rowsets.md). *TRowset* может быть любым типом набора строк, перечисленных в [типы наборов строк](../../data/oledb/accessors-and-rowsets.md). *Тип TMultiple* указывает тип результата (один или несколько результирующих наборов).  
  
 [Мастер потребителя ATL OLE DB](../../atl/reference/atl-ole-db-consumer-wizard.md) позволяет указать, следует ли объект команд или таблиц.  
  
-   Для источников данных без команд, можно использовать `CTable` класса. Обычно он используется для простых наборов строк, которые не указаны другие параметры и не требуется нескольких результатов. Этот простой класс открывает таблицы при работе с источником данных с помощью имени таблицы, указанной вами.  
  
-   Для источников данных, которые поддерживают команд, можно использовать `CCommand` вместо этого класс. Чтобы выполнить команду, вызовите [откройте](../../data/oledb/ccommand-open.md) для данного класса. В качестве альтернативы можно вызвать `Prepare` для подготовки команды, которую требуется выполнить более одного раза.  
  
     **CCommand** имеет три аргумента шаблона: тип метода доступа, тип набора строк и тип результата (`CNoMultipleResults`, по умолчанию или `CMultipleResults`). При указании `CMultipleResults`, `CCommand` поддерживает класс **IMultipleResults** интерфейса и обрабатывает несколько наборов строк. [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) образце показано, как обрабатывать несколько результатов.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)