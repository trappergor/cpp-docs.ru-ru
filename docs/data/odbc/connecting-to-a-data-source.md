---
title: Соединение с источником данных | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b6a33f1e2421c56f89184d26185903b4ec7859e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="connecting-to-a-data-source"></a>Подключение к источнику данных
Источник данных ODBC представляет собой определенный набор данных, сведения, необходимые для доступа к ним и расположение источника данных, которое можно описать с помощью имени источника данных. С точки зрения программы источник данных содержит данные, СУБД, сеть (если есть) и ODBC.  
  
 Для доступа к данным, предоставленным источника данных, программа сначала необходимо установить соединение с источником данных. Все доступ к данным осуществляется через это соединение.  
  
 Подключение к источнику данных инкапсулируется классом [CDatabase](../../mfc/reference/cdatabase-class.md). Если `CDatabase` объект подключен к источнику данных, вы можете:  
  
-   Создать [наборы записей](../../mfc/reference/crecordset-class.md), которые выбирают записи из таблиц или запросов.  
  
-   Управление [транзакции](../../data/odbc/transaction-odbc.md), поэтому вся пакетной обработки обновления являются зафиксированы в источнике данных за один раз (или вся транзакция откатывается и источник данных не изменяется) — Если источник данных поддерживает требуемый уровень транзакций.  
  
-   Непосредственное выполнение [SQL](../../data/odbc/sql.md) инструкции.  
  
 Завершив работу соединения с источником данных, закройте `CDatabase` объекта и уничтожить его или использовать его для нового соединения. Дополнительные сведения о подключениях к источнику данных см. в разделе [источника данных (ODBC)](../../data/odbc/data-source-odbc.md).  
  
## <a name="see-also"></a>См. также  
 [ODBC и MFC](../../data/odbc/odbc-and-mfc.md)