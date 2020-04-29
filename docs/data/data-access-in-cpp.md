---
title: Доступ к данным в Visual C++
ms.date: 03/28/2017
helpviewer_keywords:
- Visual C++, data access applications
- databases [C++]
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 95da6237-bbe2-480a-ae50-3a520051ceff
ms.openlocfilehash: 42c36259b14a7f0341e383bb3a7f2760bab165aa
ms.sourcegitcommit: fcc3aeb271449f8be80348740cffef39ba543407
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82538586"
---
# <a name="data-access-in-visual-c"></a>Доступ к данным в Visual C++

Практически все базы данных, как SQL, так и NoSQL, предоставляют интерфейс для собственных приложений C++. Отраслевой стандарт для такого интерфейса — ODBC. Этот интерфейс поддерживается всеми основными базами данных SQL и многими базами данных NoSQL. Для продуктов, поставщиком которых является не Майкрософт, обратитесь к поставщику продукта для получения дополнительных сведений. Также доступны сторонние библиотеки с различными условиями лицензии.

С 2011 года Майкрософт использует ODBC в качестве стандартного интерфейса для подключения собственных приложений к базам данных Microsoft SQL Server, как к локальным, так и в облаке. Дополнительные сведения см. в разделе [Программирование доступа к данным \(MFC-ATL\)](data-access-programming-mfc-atl.md). Библиотеки C++/CLI могут использовать собственные драйверы ODBC или ADO.NET. Дополнительные сведения см. в статьях [доступ к данным с помощью ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md) и [доступ к данным в Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

## <a name="in-this-section"></a>В этом разделе

[Программирование доступа к данным (MFC/ATL)](data-access-programming-mfc-atl.md)<br/>
Описывает программирование доступа к данным прежних версий с помощью Visual C++, когда предпочтительным способом является использование одной из библиотек классов, например Active Template Class Library (ATL), или библиотеки Microsoft Foundation Class (MFC), которые упрощают работу с API базы данных.

[Открытие подключения к базе данных (ODBC)](odbc/open-database-connectivity-odbc.md)<br/>
Библиотека Microsoft Foundation Classes (MFC) предоставляет классы для разработки программ с использованием интерфейса ODBC.

[Программирование OLE DB](oledb/ole-db-programming.md)<br/>
В целом устаревший интерфейс, который по-прежнему требуется в некоторых сценариях, особенно при программировании на связанных серверах.

## <a name="related-topics"></a>Связанные разделы

[Подключение к базе данных SQL с помощью C и C++](/azure/sql-database/sql-database-develop-cplusplus-simple)<br/>
Подключение к базе данных SQL Azure из приложений на C или C++.

[Клиентская библиотека службы хранилища Microsoft Azure для C++](https://github.com/Azure/azure-storage-cpp)<br/>
[Хранилище Azure](/azure/storage/common/storage-introduction) представляет собой решение облачного хранилища для современных приложений, которым необходима устойчивость, доступность и масштабируемость для удовлетворения потребностей пользователей. Подключитесь к хранилищу Azure из приложения на языке C++ с помощью клиентской библиотеки хранилища Azure для C++.

[Драйвер ODBC для SQL Server](/sql/connect/odbc/microsoft-odbc-driver-for-sql-server)<br/>
Последняя версия драйвера ODBC предоставляет надежный доступ к данным Microsoft SQL Server и базы данных SQL Microsoft Azure для приложений на C/C++. Предоставляет поддержку для функций, включая функцию постоянного шифрования, Azure Active Directory и группы доступности AlwaysOn. Также доступен для MacOS и Linux.

[Драйвер OLE DB для SQL Server](/sql/connect/oledb/oledb-driver-for-sql-server)<br/>
Последняя версия драйвера OLE DB является автономным программным интерфейсом (API) для доступа к данным, который поддерживает Microsoft SQL Server и базу данных SQL Microsoft Azure.

[Центр разработчиков Microsoft Azure C и C++](https://azure.microsoft.com/develop/cpp/)<br/>
Azure позволяет легко создавать приложения C++, обладающие высокой гибкостью, масштабируемостью и надежностью, с помощью тех инструментов, которые вам нравятся.

[Использование хранилища BLOB-объектов из C++](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs)<br/>
Хранилище BLOB-объектов Azure — это служба, которая хранит неструктурированные данные в облаке в качестве объектов или больших двоичных объектов. В хранилище BLOB-объектов могут храниться текстовые или двоичные данные любого типа, например документы, файлы мультимедиа или установщики приложений. Хранилище BLOB-объектов иногда также называют хранилищем объектов.

[Справочник по программированию ODBC](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference)<br/>
Интерфейс ODBC предназначен для использования с языком программирования C. Использование интерфейса ODBC охватывает три области: инструкции SQL, вызовы функций ODBC и программирование на языке C.

## <a name="see-also"></a>См. также

[C++ в Visual Studio](../overview/visual-cpp-in-visual-studio.md)
