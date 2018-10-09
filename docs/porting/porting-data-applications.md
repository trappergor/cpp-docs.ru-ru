---
title: Перенос приложений для обработки данных | Microsoft Docs
ms.custom: ''
ms.date: 05/12/2017
ms.technology:
- devlang-cpp
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 8d10c285-c13f-4e6e-a09e-5ee0f2666b44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3dcbab39bdf6a9a944b3cd6200302d89a30d163d
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820754"
---
# <a name="porting-data-applications"></a>Перенос приложений для обработки данных
С течением времени в Visual C++ появлялись различные способы работы с базами данных. В 2011 г. корпорация Майкрософт объявила о том, что интерфейс ODBC теперь станет предпочтительной технологией для доступа к продуктам SQL Server из машинного кода. ODBC является отраслевым стандартом, и его использование гарантирует максимально простой перенос кода под различные платформы и источники данных. ODBC поддерживается большинством продуктов SQL для работы с базами данных и многими продуктами NoSQL. Его можно использовать напрямую путем вызова низкоуровневых API-интерфейсов ODBC, либо можно использовать классы-оболочки MFC или сторонние библиотеки-оболочки C++. 

OLE DB — это низкоуровневый высокопроизводительный API-интерфейс на основе спецификации COM, который поддерживается только в Windows. Используйте OLE DB, если ваша программа осуществляет доступ к [связанным серверам](/sql/relational-databases/linked-servers/linked-servers-database-engine). Библиотека ATL содержит шаблоны для OLE DB, упрощающие создание настраиваемых поставщиков и объектов-получателей OLE DB. Самая последняя версия OLE DB входит в комплект поставки SQL Native Client 11.  

Если предыдущие версии вашего приложения использовали OLE DB или интерфейс ADO более высокого уровня для подключения к SQL Server и вы не обращаетесь к связанным серверам, подумайте о переносе приложения на ODBC в ближайшем будущем. Если вам не требуется возможность переноса на множество платформ или новейшие функции SQL Server, вы можете использовать поставщик Microsoft OLE DB для ODBC (MSDASQL).  MSDASQL позволяет приложениям, созданным на базе OLE DB и ADO (где внутри тоже используется OLEDB), получать доступ к источникам данных с помощью драйвера ODBC. Так как MSDASQL является еще одним уровнем преобразования, он может повлиять на работу баз данных. Вам нужно будет проанализировать, насколько сильно будет затронуто ваше приложение. MSDASQL поставляется с операционной системой Windows. Windows Server 2008 и Windows Vista с пакетом обновления 1 (SP1) являются первыми выпусками Windows, включающими 64-разрядную версию технологии.

Компонент SQL Native Client (SNAC), который упаковывает драйверы OLE DB и ODBC в одну DLL-библиотеку, не рекомендуется использовать для приложений ODBC. Версия SNAC из SQL Server 2012 (SQLNCLI11. DLL) поставляется с SQL Server 2016, так как от нее зависят другие компоненты SQL Server. Но новые приложения C++, которые подключаются через ODBC к SQL Server или базам данных SQL Azure, должны использовать [самую последнюю версию драйвера ODBC](/sql/connect/odbc/download-odbc-driver-for-sql-server). Подробнее см. в разделе [SQL Server Native Client Programming](/sql/relational-databases/native-client/sql-server-native-client-programming) (Программирование с SQL Server Native Client).

Если вы работаете с C++/CLI, вы можете продолжать использовать ADO.NET как и раньше. Подробнее см. в разделах [Доступ к данным с помощью ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) и [Доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).  
  
- Помимо классов-оболочек ODBC в MFC содержатся классы-оболочки DAO для подключения к базам данных Access.  Но технология DAO устарела. Любой код, основанный на `CDaoDatabase` или `CDaoRecordset`, необходимо обновить. 

Дополнительные сведения об истории технологий доступа к данным в Microsoft Windows см. на странице [Microsoft Data Access Components в Википедии](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components).  

## <a name="see-also"></a>См. также  
 
[Доступ к данным в Visual C++](../data/data-access-in-cpp.md)<br/>
[Microsoft Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
[Схема технологий доступа к данным](https://msdn.microsoft.com/library/ms810810.aspx)  