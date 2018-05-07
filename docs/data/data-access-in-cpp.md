---
title: Доступ к данным в Visual C++ | Документы Microsoft
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, data access applications
- databases [C++]
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 95da6237-bbe2-480a-ae50-3a520051ceff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bb74d27af485f765e1330bc83ab196e1d9ba6b5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="data-access-in-visual-c"></a>Доступ к данным в Visual C++

Практически все базы данных, как SQL, так и NoSQL, предоставляют интерфейс для собственных приложений C++. Отраслевой стандарт для такого интерфейса — ODBC. Этот интерфейс поддерживается всеми основными базами данных SQL и многими базами данных NoSQL. Для продуктов, поставщиком которых является не Майкрософт, обратитесь к поставщику продукта для получения дополнительных сведений. Также доступны сторонние библиотеки с различными условиями лицензии.

С 2011 года Майкрософт использует ODBC в качестве стандартного интерфейса для подключения собственных приложений к базам данных Microsoft SQL Server, как к локальным, так и в облаке. Дополнительные сведения см. в разделе [Программирование доступа к данным \(MFC-ATL\)](data-access-programming-mfc-atl.md). Библиотеки C++/CLI могут использовать собственные драйверы ODBC или ADO.NET. Дополнительные сведения см. в разделах [Доступ к данным с помощью ADO.NET (C++/CLI)](/dotnet/data-access-using-adonet-cpp-cli.md) и [Доступ к данным в Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

## <a name="in-this-section"></a>В этом разделе
[Программирование доступа к данных (MFC/ATL)](data-access-programming-mfc-atl.md) программирование с помощью Visual C++, где предпочтительным способом является использование одной из библиотек классов, например Active Template класс Library (ATL) или библиотеки Microsoft Foundation Class (MFC), доступа к данным прежних версий описывает который упрощают работу с API базы данных.

[Откройте Database Connectivity (ODBC)](odbc/open-database-connectivity-odbc.md) библиотеки Microsoft Foundation Classes (MFC) предоставляет классы для программирования с Open Database Connectivity (ODBC).

[OLE DB программирования](oledb/ole-db-programming.md) основном устаревший интерфейс, который по-прежнему требуется в некоторых случаях, особенно при программировании связанных серверов.

## <a name="related-topics"></a>См. также
[Подключение к базе данных SQL с помощью C и C++](/azure/sql-database/sql-database-develop-cplusplus-simple) подключитесь к базе данных SQL Azure из приложения C или C++.

[Клиентская библиотека хранилища Microsoft Azure для C++](https://github.com/Azure/azure-storage-cpp)
[хранилища Azure](/azure/storage/storage-introduction) является решение облачного хранилища для современных приложений, которые зависят от надежности, доступности и масштабируемости для удовлетворения потребностей их Клиенты. Подключитесь к хранилищу Azure из приложения на языке C++ с помощью клиентской библиотеки хранилища Azure для C++.

[ODBC Driver 13.1 for SQL Server — выпущена Windows](https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server) последнюю версию драйвера ODBC обеспечивает надежный доступ к данным Microsoft SQL Server 2016 Microsoft Azure SQL Database приложений на основе C/C++. Предоставляет поддержку для функций, в том числе постоянное шифрование, Azure Active Directory и групп доступности AlwaysOn. Также доступен для MacOS и Linux.     
 
[Собственный клиент SQL Server](/sql/relational-databases/native-client/sql-server-native-client-programming) собственный клиент SQL Server — данных автономного доступа прикладной программный интерфейс (API) используется для OLE DB и ODBC, который поддерживает SQL Server 2005 до SQL Server 2014. В новых приложениях следует использовать драйвер ODBC версии 13.1 для SQL Server.

[Центр разработчиков C++ и Microsoft Azure C](https://azure.microsoft.com/develop/cpp/) Azure позволяет легко создавать приложения C++ с Повышенная гибкость, масштабируемость и надежность, с помощью средств, которые вы предпочитаете.    

[Использование хранилища BLOB-объектов из C++](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs) хранилища больших двоичных объектов Azure — это служба, неструктурированные данные хранятся в облаке как большие двоичные объекты и объекты. В хранилище BLOB-объектов можно хранить любые типы текстовых или двоичных данных, таких как документы, файлы мультимедиа или установщики приложений. Хранилище BLOB-объектов также называют хранилищем объектов.

[ Справочник по программированию ODBC](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference) интерфейса ODBC предназначен для использования с языка программирования. Использование интерфейса ODBC охватывает три области: инструкции SQL, вызовы функций ODBC и программирование на языке C.

## <a name="see-also"></a>См. также
[Visual C++](../visual-cpp-in-visual-studio.md)
