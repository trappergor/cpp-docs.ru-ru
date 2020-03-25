---
title: Использование методов ручного доступа
ms.date: 10/24/2018
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
ms.openlocfilehash: a6c0e5236702229a61a828344ba5d0d288898aee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209330"
---
# <a name="using-manual-accessors"></a>Использование методов ручного доступа

При обработке неизвестной команды необходимо выполнить четыре действия:

- Определение параметров

- Выполнение команды

- Определение выходных столбцов

- Проверьте, есть ли несколько возвращаемых наборов строк

Чтобы выполнить эти действия с помощью шаблонов потребителей OLE DB, используйте класс `CManualAccessor` и выполните следующие действия.

1. Откройте объект `CCommand` с `CManualAccessor` в качестве параметра шаблона.

    ```cpp
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;
    ```

1. Выполните запрос к сеансу для интерфейса `IDBSchemaRowset` и используйте набор строк Parameters процедуры. Если интерфейс `IDBSchemaRowset` недоступен, запросите интерфейс `ICommandWithParameters`. Вызовите `GetParameterInfo` для получения сведений. Если ни один из интерфейсов недоступен, можно предположить, что параметры отсутствуют.

1. Для каждого параметра вызовите `AddParameterEntry`, чтобы добавить параметры и задать их.

1. Откройте набор строк, но установите для параметра BIND значение **false**.

1. Вызовите `GetColumnInfo`, чтобы получить выходные столбцы. Используйте `AddBindEntry`, чтобы добавить выходной столбец в привязку.

1. Вызовите `GetNextResult`, чтобы определить, доступны ли дополнительные наборы строк. Повторите шаги с 2 по 5.

Пример метода доступа вручную см. в разделе `CDBListView::CallProcedure` в образце [дбвиевер](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) .

## <a name="see-also"></a>См. также раздел

[Использование методов доступа](../../data/oledb/using-accessors.md)
