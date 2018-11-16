---
title: Доступ к данным, программирование (MFC-ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
ms.openlocfilehash: 8341cf715c96783880fd83f1b8fbb197dbff6046
ms.sourcegitcommit: b08ddf79ea76369c388173913e4e8f6fd8ad02d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51830482"
---
# <a name="data-access-programming-mfcatl"></a>Программирование доступа к данным (MFC/ATL)

С течением времени в Visual C++ появлялись различные способы работы с базами данных. В 2011 г. корпорация Майкрософт объявила о том, что интерфейс ODBC теперь станет предпочтительной технологией для доступа к продуктам SQL Server из машинного кода. ODBC является отраслевым стандартом, и его использование гарантирует максимально простой перенос кода под различные платформы и источники данных. ODBC поддерживается большинством продуктов SQL для работы с базами данных и многими продуктами NoSQL. Его можно использовать напрямую путем вызова низкоуровневых API-интерфейсов ODBC, либо можно использовать классы-оболочки MFC или сторонние библиотеки-оболочки C++.

OLE DB — это низкоуровневый высокопроизводительный API-интерфейс на основе спецификации COM, который поддерживается только в Windows. Используйте OLE DB, если ваша программа осуществляет доступ к [связанным серверам](/sql/relational-databases/linked-servers/linked-servers-database-engine). Библиотека ATL содержит шаблоны для OLE DB, упрощающие создание настраиваемых поставщиков и объектов-получателей OLE DB. Самая последняя версия OLE DB входит в комплект поставки SQL Native Client 11.

Если предыдущие версии вашего приложения использовали OLE DB или интерфейс ADO более высокого уровня для подключения к SQL Server и вы не обращаетесь к связанным серверам, подумайте о переносе приложения на ODBC в ближайшем будущем. Если вам не требуется возможность переноса на множество платформ или новейшие функции SQL Server, вы можете использовать поставщик Microsoft OLE DB для ODBC (MSDASQL).  MSDASQL позволяет приложениям, созданным на базе OLE DB и ADO (где внутри тоже используется OLEDB), получать доступ к источникам данных с помощью драйвера ODBC. Как и в случае с уровнем преобразования, MSDASQL может повлиять на производительность базы данных. Необходимо протестировать, чтобы определить, является ли влияние значительные для вашего приложения. MSDASQL поставляется с операционной системой Windows. Windows Server 2008 и Windows Vista с пакетом обновления 1 (SP1) являются первыми выпусками Windows, включающими 64-разрядную версию технологии.

Компонент SQL Native Client (SNAC), который упаковывает драйверы OLE DB и ODBC в одну DLL-библиотеку, не рекомендуется использовать для приложений ODBC. Версия SNAC из SQL Server 2012 (SQLNCLI11. DLL) поставляется с SQL Server 2016, так как от нее зависят другие компоненты SQL Server. Но новые приложения C++, которые подключаются через ODBC к SQL Server или базам данных SQL Azure, должны использовать [самую последнюю версию драйвера ODBC](https://docs.microsoft.com/sql/connect/odbc/download-odbc-driver-for-sql-server). Подробнее см. в разделе [SQL Server Native Client Programming](/sql/relational-databases/native-client/sql-server-native-client-programming) (Программирование с SQL Server Native Client).

Если вы работаете с C++/CLI, вы можете продолжать использовать ADO.NET как и раньше. Подробнее см. в разделах [Доступ к данным с помощью ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) и [Доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).

- Помимо классов-оболочек ODBC MFC предоставляет классы-оболочки объектов доступа к данным (DAO) для подключения к базам данных Access.  Но технология DAO устарела. Любой код на основе CDaoDatabase или CDaoRecordset требует обновления.

Дополнительные сведения об истории технологий доступа к данным в Microsoft Windows см. на странице [Microsoft Data Access Components в Википедии](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).

## <a name="see-also"></a>См. также

[Доступ к данным](data-access-in-cpp.md)<br/>
[Microsoft Open Database Connectivity (ODBC)](https://docs.microsoft.com/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
[Схема технологий доступа к данным](https://msdn.microsoft.com/library/ms810810.aspx)