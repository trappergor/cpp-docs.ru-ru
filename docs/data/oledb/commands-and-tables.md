---
title: Команды и таблицы
ms.date: 11/19/2018
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
ms.openlocfilehash: 0d5f6bd8d5f813497cba399e5c071f43dc1a7c4d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211527"
---
# <a name="commands-and-tables"></a>Команды и таблицы

Команды и таблицы позволяют получить доступ к наборам строк; то есть открытые наборы строк, выполнение команд и привязка столбцов. Классы [CCommand](../../data/oledb/ccommand-class.md) и [CTable](../../data/oledb/ctable-class.md) создают экземпляры объектов Command и Table соответственно. Эти классы являются производными от [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) , как показано на следующем рисунке.

![CCommand и CTable](../../data/oledb/media/vccommandstables.gif "CCommand и CTable")<br/>
Классы команд и таблиц

В предыдущей таблице `TAccessor` может быть любым типом метода доступа, перечисленным в [типах методов доступа](../../data/oledb/accessors-and-rowsets.md). `TRowset` может быть любым типом набора строк, указанным в [типах наборов строк](../../data/oledb/accessors-and-rowsets.md). `TMultiple` указывает тип результата (один или несколько результирующих наборов).

[Мастер ATL OLE DB Consumer](../../atl/reference/atl-ole-db-consumer-wizard.md) позволяет указать, нужно ли использовать объект Command или Table.

- Для источников данных без команд можно использовать класс `CTable`. Обычно он используется для простых наборов строк, которые не задают никаких параметров и не требует нескольких результатов. Этот простой класс открывает таблицу в источнике данных, используя указанное имя таблицы.

- Для источников данных, поддерживающих команды, вместо них можно использовать класс `CCommand`. Чтобы выполнить команду, вызовите метод [Open](../../data/oledb/ccommand-open.md) для этого класса. В качестве альтернативы можно вызвать `Prepare` для подготовки команды, которую требуется выполнить более одного раза.

   `CCommand` имеет три аргумента шаблона: тип метода доступа, тип набора строк и тип результата (`CNoMultipleResults`, по умолчанию или `CMultipleResults`). При указании `CMultipleResults`класс `CCommand` поддерживает интерфейс `IMultipleResults` и обрабатывает несколько наборов строк. В примере [дбвиевер](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) показано, как управлять несколькими результатами.

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)
