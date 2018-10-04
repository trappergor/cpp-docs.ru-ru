---
title: Атрибуты потребителя OLE DB (C++ COM) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], database
- attributes [C++/CLI], data access
- databases [C++], attributes
- OLE DB consumers [C++], attributes
- database attributes [C++/CLI]
- attributes [C++/CLI], OLE DB consumer
ms.assetid: 017b591f-8f9a-42b4-84d5-cc42a21ab0cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35051c565a18ba61de53813ce57be147140cc468
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792524"
---
# <a name="ole-db-consumer-attributes"></a>Атрибуты потребителя OLE DB
Атрибуты потребителя OLE DB вставки кода, на основе [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md), чтобы создать рабочий OLE DB получатель, который выполняет задачи, такие как Открытие таблицы, выполнения команд и доступ к данным.
  
|Атрибут|Описание|
|---------------|-----------------|
|[db_accessor](db-accessor.md)|Связывает столбцы в наборе строк и привязывает их к соответствующей карты метода доступа.|
|[db_column](db-column.md)|Связывает указанный столбец набора строк.|
|[db_command](db-command.md)|Выполняет команду OLE DB.|
|[db_param](db-param.md)|Связывает указанный член переменной с параметром ввода или вывода.|
|[db_source](db-source.md)|Создает и инкапсулирует соединение, через поставщика, к источнику данных.|
|[db_table](db-table.md)|Открывает таблицу OLE DB.|
  
## <a name="see-also"></a>См. также

[Список атрибутов по группам](attributes-by-group.md)