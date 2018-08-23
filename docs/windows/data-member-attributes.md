---
title: Атрибуты членов данных | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5eb54889cb6e2590c334ad4e9aed497a945cc99d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601787"
---
# <a name="data-member-attributes"></a>Атрибуты членов данных

Следующие атрибуты применяются на данные-члены в классе, компонентный класс или интерфейс.

|Атрибут|Описание:|
|---------------|-----------------|
|[db_accessor](../windows/db-accessor.md)|Группы `db_column` атрибуты, которые участвуют в `IAccessor`-привязку на основе.|
|[db_column](../windows/db-column.md)|Связывает указанный столбец набора строк.|
|[db_command](../windows/db-command.md)|Создает команду OLE DB.|
|[db_param](../windows/db-param.md)|Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.|
|[db_source](../windows/db-source.md)|Создает подключение к источнику данных.|
|[db_table](../windows/db-table.md)|Открывает таблицу OLE DB.|
|[defaultbind](../windows/defaultbind.md)|Указывает единственное свойство, представляющим объект наилучшим образом.|
|[displaybind](../windows/displaybind.md)|Указывает свойство, которое должно отображаться пользователю как связываемая.|
|[id](../windows/id.md)|Указывает идентификатор DISPID для функцию-член (свойство или метод, в интерфейс или диспетчерский интерфейс).|
|[Диапазон](../windows/range-cpp.md)|Указывает диапазон допустимых значений для полей, значения которых устанавливаются во время выполнения и аргументы.|
|[rdx](../windows/rdx.md)|Создает раздел реестра или изменяет существующий раздел реестра.|
|[readonly](../windows/readonly-cpp.md)|Запрещает назначение элементу данных.|
|[requestedit](../windows/requestedit.md)|Указывает, что свойство поддерживает `OnRequestEdit` уведомлений.|

## <a name="see-also"></a>См. также

[Список атрибутов по использованию](../windows/attributes-by-usage.md)