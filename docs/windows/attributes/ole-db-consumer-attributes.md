---
title: OLE DB атрибуты потребителя (C++ com)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], database
- attributes [C++/CLI], data access
- databases [C++], attributes
- OLE DB consumers [C++], attributes
- database attributes [C++/CLI]
- attributes [C++/CLI], OLE DB consumer
ms.assetid: 017b591f-8f9a-42b4-84d5-cc42a21ab0cc
ms.openlocfilehash: 67f58d6dd32360248c6437f66fa7042871bc4ea6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214717"
---
# <a name="ole-db-consumer-attributes"></a>Атрибуты потребителя OLE DB
OLE DB атрибуты потребителя вставляют код на основе [шаблонов OLE DB потребителей](../../data/oledb/ole-db-consumer-templates-reference.md), чтобы создать рабочий OLE DB потребитель, выполняющий такие задачи, как открытие таблиц, выполнение команд и доступ к данным.

|attribute|Description|
|---------------|-----------------|
|[db_accessor](db-accessor.md)|Привязывает столбцы в наборе строк и привязывает их к соответствующим картам метода доступа.|
|[db_column](db-column.md)|Привязывает указанный столбец к набору строк.|
|[db_command](db-command.md)|Выполняет команду OLE DB.|
|[db_param](db-param.md)|Связывает указанную переменную элемента с входным или выходным параметром.|
|[db_source](db-source.md)|Создает и инкапсулирует соединение (через поставщика) к источнику данных.|
|[db_table](db-table.md)|Открывает таблицу OLE DB.|

## <a name="see-also"></a>См. также раздел

[Список атрибутов по группам](attributes-by-group.md)
