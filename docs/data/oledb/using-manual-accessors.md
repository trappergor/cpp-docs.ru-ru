---
title: Использование методов ручного доступа
ms.date: 10/24/2018
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
ms.openlocfilehash: 4a7e2dcde20cdb06a2f4e708149e24ee7144597c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311999"
---
# <a name="using-manual-accessors"></a>Использование методов ручного доступа

Существует четыре какие действия можно выполнить при обработке Неизвестная команда:

- Определение параметров

- Выполните команду

- Определить выходные столбцы.

- Проверить, есть несколько наборов строк, возвращаемого значения

Чтобы выполнить эти действия с Шаблоны потребителей OLE DB, используйте `CManualAccessor` класса и выполните следующие действия:

1. Откройте `CCommand` со `CManualAccessor` как параметр шаблона.

    ```cpp
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;
    ```

1. Запрос сеанса для `IDBSchemaRowset` интерфейса и использовать набор строк параметров процедуры. Если `IDBSchemaRowset` интерфейс недоступен, запрашивать `ICommandWithParameters` интерфейс. Вызовите `GetParameterInfo` сведения. Если ни один из интерфейсов, можно предположить, что параметры отсутствуют.

1. Для каждого параметра вызова `AddParameterEntry` добавить параметры и установить их.

1. Открыть набор строк, но задать для параметра привязки **false**.

1. Вызовите `GetColumnInfo` для получения выходных столбцов. Используйте `AddBindEntry` добавляемый привязки выходного столбца.

1. Вызовите `GetNextResult` для определения того, если доступны дополнительные наборы строк. Повторите шаги 2 – 5.

Пример метода доступа вручную, см. в разделе `CDBListView::CallProcedure` в [DBVIEWER](https://github.com/Microsoft/VCSamples) образца.

## <a name="see-also"></a>См. также

[Использование методов доступа](../../data/oledb/using-accessors.md)