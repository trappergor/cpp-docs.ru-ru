---
title: Подключение к источнику данных
ms.date: 11/04/2016
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
ms.openlocfilehash: b7bb0ffe169fd9b4167e6af4b772df23acf02212
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575530"
---
# <a name="connecting-to-a-data-source"></a>Подключение к источнику данных

Источник данных ODBC — это определенный набор данных, сведения, необходимые для доступа к этим данным, а также расположение источника данных, которые можно описать с помощью имени источника данных. С точки зрения программы источник данных содержит данные, СУБД, сети (если таковые имеются) и ODBC.

Для доступа к данным, предоставляемые источником данных, программа сначала необходимо установить соединение с источником данных. Доступа ко всем данным осуществляется через это подключение.

Подключение к источнику данных инкапсулируется классом [CDatabase](../../mfc/reference/cdatabase-class.md). Когда `CDatabase` объект подключен к источнику данных, вы можете:

- Создать [наборы записей](../../mfc/reference/crecordset-class.md), которые выбирают записи из таблиц или запросов.

- Управление [транзакции](../../data/odbc/transaction-odbc.md), так что все пакетной обработки обновления фиксируются к источнику данных за один раз (или вся транзакция откатывается и источник данных не изменяется) — Если источник данных поддерживает необходимый уровень транзакции.

- Непосредственное выполнение [SQL](../../data/odbc/sql.md) инструкций.

Когда вы закончите работу с подключение к источнику данных, закройте `CDatabase` объекта и уничтожить его или использовать повторно для нового соединения. Дополнительные сведения о подключениях см. в разделе [источника данных (ODBC)](../../data/odbc/data-source-odbc.md).

## <a name="see-also"></a>См. также

[ODBC и MFC](../../data/odbc/odbc-and-mfc.md)