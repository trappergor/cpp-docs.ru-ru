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
- attributes [C++/CLI], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fc5bfb34e2df0fad363e499cc5a7277d15d14d1
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318854"
---
# <a name="data-member-attributes"></a>Атрибуты членов данных

Следующие атрибуты применяются на данные-члены в классе, компонентный класс или интерфейс.

|Атрибут|Описание|
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