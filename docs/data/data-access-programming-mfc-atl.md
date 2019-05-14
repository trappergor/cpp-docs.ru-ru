---
title: Доступ к данным, программирование (MFC-ATL)
ms.date: 11/16/2018
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
ms.openlocfilehash: e71e16bef29239e0c6a391b2d5e2129042cd52fa
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221843"
---
# <a name="data-access-programming-mfcatl"></a>Программирование доступа к данным (MFC/ATL)

С течением времени в Visual C++ появлялись различные способы работы с базами данных. В 2011 г. Корпорация Microsoft объявила, что он переводит на Open Database Connectivity (ODBC) станет предпочтительной технологией для доступа к продуктов SQL Server из машинного кода. ODBC является отраслевым стандартом, и его использование гарантирует максимально простой перенос кода под различные платформы и источники данных. ODBC поддерживается большинством продуктов SQL для работы с базами данных и многими продуктами NoSQL. Его можно использовать напрямую путем вызова низкоуровневых API-интерфейсов ODBC, либо можно использовать классы-оболочки MFC или сторонние библиотеки-оболочки C++.

OLE DB — это низкоуровневый высокопроизводительный API-интерфейс на основе спецификации COM, который поддерживается только в Windows. Используйте OLE DB, если ваша программа осуществляет доступ к [связанным серверам](/sql/relational-databases/linked-servers/linked-servers-database-engine). Библиотека ATL содержит шаблоны для OLE DB, упрощающие создание настраиваемых поставщиков и объектов-получателей OLE DB. Последние поставщик для Microsoft SQL Server можно найти в документации по [драйвер OLE DB для SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server).

## <a name="porting-data-applications"></a>Перенос данных приложений

Если предыдущие версии вашего приложения использует OLE DB или интерфейс ADO более высокого уровня для подключения к SQL Server, стоит рассмотреть переход к последнему [драйвер OLE DB для SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server) чтобы можно было воспользоваться новыми функциями Microsoft SQL Server. Другой вариант, если не требуется переносимость платформ или новейшие функции SQL Server, можно возможно использовать поставщик Microsoft OLE DB для ODBC (MSDASQL).  MSDASQL позволяет приложениям, созданным на базе OLE DB и ADO (где внутри тоже используется OLEDB), получать доступ к источникам данных с помощью драйвера ODBC. Так как MSDASQL является еще одним уровнем преобразования, он может повлиять на работу баз данных. Вам нужно будет проанализировать, насколько сильно будет затронуто ваше приложение. MSDASQL поставляется с операционной системой Windows. Windows Server 2008 и Windows Vista с пакетом обновления 1 (SP1) являются первыми выпусками Windows, включающими 64-разрядную версию технологии.

Если ваш C++ приложение подключается к SQL Server или базы данных SQL Azure с помощью ODBC, он должен использовать [последнюю версию драйвера ODBC](/sql/connect/odbc/download-odbc-driver-for-sql-server).

Если вы работаете с C++/CLI, вы можете продолжать использовать ADO.NET как и раньше. Подробнее см. в разделах [Доступ к данным с помощью ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) и [Доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).

- Помимо классов-оболочек ODBC, в MFC содержатся классы-оболочки DAO для подключения к базам данных Access.  Но технология DAO устарела. Любой код на основе CDaoDatabase или CDaoRecordset требует обновления.

Дополнительные сведения об истории технологий доступа к данным в Microsoft Windows см. на странице [Microsoft Data Access Components в Википедии](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).

## <a name="see-also"></a>См. также

[Доступ к данным](data-access-in-cpp.md)<br/>
[Microsoft Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
