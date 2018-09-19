---
title: Доступ к данным в Visual C++ | Документация Майкрософт
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
ms.openlocfilehash: c8e2fc86d15472bd4ab63e472df99bb69393b386
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060308"
---
# <a name="data-access-in-visual-c"></a>Доступ к данным в Visual C++

Практически все базы данных, как SQL, так и NoSQL, предоставляют интерфейс для собственных приложений C++. Отраслевой стандарт для такого интерфейса — ODBC. Этот интерфейс поддерживается всеми основными базами данных SQL и многими базами данных NoSQL. Для продуктов, поставщиком которых является не Майкрософт, обратитесь к поставщику продукта для получения дополнительных сведений. Также доступны сторонние библиотеки с различными условиями лицензии.

С 2011 года Майкрософт использует ODBC в качестве стандартного интерфейса для подключения собственных приложений к базам данных Microsoft SQL Server, как к локальным, так и в облаке. Дополнительные сведения см. в разделе [Программирование доступа к данным \(MFC-ATL\)](data-access-programming-mfc-atl.md). Библиотеки C++/CLI могут использовать собственные драйверы ODBC или ADO.NET. Дополнительные сведения см. в разделах [Доступ к данным с помощью ADO.NET (C++/CLI)](/dotnet/data-access-using-adonet-cpp-cli.md) и [Доступ к данным в Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

## <a name="in-this-section"></a>В этом разделе

[Доступ к данным, программирование (MFC/ATL)](data-access-programming-mfc-atl.md)<br/>
Описывает программирование доступа к данным прежних версий с помощью Visual C++, когда предпочтительным способом является использование одной из библиотек классов, например Active Template Class Library (ATL), или библиотеки Microsoft Foundation Class (MFC), которые упрощают работу с API базы данных.

[Интерфейс ODBC](odbc/open-database-connectivity-odbc.md)<br/>
Библиотека Microsoft Foundation Classes (MFC) предоставляет классы для разработки программ с использованием интерфейса ODBC.

[Программирование объектов OLE DB](oledb/ole-db-programming.md)<br/>
Главным образом прежних версий интерфейс, который по-прежнему требуется в некоторых сценариях, в частности, при программировании на связанных серверах.

## <a name="related-topics"></a>См. также

[Подключение к базе данных SQL с помощью C и C++](/azure/sql-database/sql-database-develop-cplusplus-simple)<br/>
Подключение к базе данных SQL Azure из приложений C или C++.

[Клиентская библиотека хранилища Microsoft Azure для C++](https://github.com/Azure/azure-storage-cpp)<br/>
[Хранилище Azure](/azure/storage/storage-introduction) представляет собой решение облачного хранилища для современных приложений, которым необходима устойчивость, доступность и масштабируемость для удовлетворения потребностей пользователей. Подключитесь к хранилищу Azure из приложения на языке C++ с помощью клиентской библиотеки хранилища Azure для C++.

[ODBC Driver 13.1 for SQL Server — Windows выпуска](https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server)<br/>
Последняя версия драйвера ODBC обеспечивает надежный доступ к базам данных SQL Microsoft Azure и Microsoft SQL Server 2016 для приложений на языках C и C++. Предоставляет поддержку для функций, включая постоянного шифрования, Azure Active Directory и группы доступности AlwaysOn. Также доступен для MacOS и Linux.     
 
[Собственный клиент SQL Server](/sql/relational-databases/native-client/sql-server-native-client-programming)<br/>
Собственный клиент SQL Server — прикладной программный интерфейс (API) для автономного доступа к данным, который используется для OLE DB и ODBC и поддерживается в версиях SQL Server начиная с SQL Server 2005 и заканчивая SQL Server 2014. В новых приложениях следует использовать драйвер ODBC версии 13.1 для SQL Server.

[Microsoft Azure C и C++ Developer Center](https://azure.microsoft.com/develop/cpp/)<br/>
Azure позволяет легко создавать приложения C++, обладающие высокой гибкостью, масштабируемостью и надежностью, с помощью тех инструментов, которые вам нравятся.    

[Использование хранилища BLOB-объектов из C++](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs)<br/>
Хранилище BLOB-объектов Azure — это служба, которая сохраняет неструктурированные данные в облаке в виде BLOB-объектов. В хранилище BLOB-объектов можно хранить любые типы текстовых или двоичных данных, таких как документы, файлы мультимедиа или установщики приложений. Хранилище BLOB-объектов также называют хранилищем объектов.

[ Справочник по программированию ODBC](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference)<br/>
Интерфейс ODBC предназначен для использования с языком программирования C. Использование интерфейса ODBC охватывает три области: инструкции SQL, вызовы функций ODBC и программирование на языке C.

## <a name="see-also"></a>См. также

[Visual C++](../visual-cpp-in-visual-studio.md)
