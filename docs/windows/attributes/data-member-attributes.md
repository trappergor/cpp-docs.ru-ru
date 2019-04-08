---
title: Атрибуты членов данных (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
ms.openlocfilehash: ad21ed16eee8cd14e8f798450ff385d5f429a280
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041154"
---
# <a name="data-member-attributes"></a>Атрибуты членов данных

Следующие атрибуты применяются на данные-члены в классе, компонентный класс или интерфейс.

|Атрибут|Описание|
|---------------|-----------------|
|[db_accessor](db-accessor.md)|Группы `db_column` атрибуты, которые участвуют в `IAccessor`-привязку на основе.|
|[db_column](db-column.md)|Связывает указанный столбец набора строк.|
|[db_command](db-command.md)|Создает команду OLE DB.|
|[db_param](db-param.md)|Связывает указанный член переменной с входным или выходным параметром и разделяет переменной.|
|[db_source](db-source.md)|Создает подключение к источнику данных.|
|[db_table](db-table.md)|Открывает таблицу OLE DB.|
|[defaultbind](defaultbind.md)|Указывает единственное свойство, представляющим объект наилучшим образом.|
|[displaybind](displaybind.md)|Указывает свойство, которое должно отображаться пользователю как связываемая.|
|[id](id.md)|Указывает идентификатор DISPID для функцию-член (свойство или метод, в интерфейс или диспетчерский интерфейс).|
|[range](range-cpp.md)|Указывает диапазон допустимых значений для полей, значения которых устанавливаются во время выполнения и аргументы.|
|[rdx](rdx.md)|Создает раздел реестра или изменяет существующий раздел реестра.|
|[readonly](readonly-cpp.md)|Запрещает назначение элементу данных.|
|[requestedit](requestedit.md)|Указывает, что свойство поддерживает уведомление `OnRequestEdit`.|

## <a name="see-also"></a>См. также

[Список атрибутов по использованию](attributes-by-usage.md)