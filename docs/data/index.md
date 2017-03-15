---
layout: LandingPage
title: "Доступ к данным в Visual C++"
translationtype: Human Translation
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: bcec6bba72b48c8fc766c2d74dc31d8e47a239f9
ms.lasthandoff: 03/06/2017

---
# <a name="data-access-in-visual-c"></a>Доступ к данным в Visual C++

Практически все базы данных, как SQL, так и NoSQL, предоставляют интерфейс для собственных приложений C++. Отраслевой стандарт для такого интерфейса — ODBC. Этот интерфейс поддерживается всеми основными базами данных SQL и многими базами данных NoSQL. Для продуктов, поставщиком которых является не Майкрософт, обратитесь к поставщику продукта для получения дополнительных сведений. Также доступны сторонние библиотеки с различными условиями лицензии.

С 2011 года Майкрософт использует ODBC в качестве стандартного интерфейса для подключения собственных приложений к базам данных Microsoft SQL Server, как к локальным, так и в облаке. Дополнительные сведения см. в разделе [Программирование доступа к данным \(MFC-ATL\)](data-access-programming-mfc-atl.md). Библиотеки C++/CLI могут использовать собственные драйверы ODBC или ADO.NET. Дополнительные сведения см. в разделах [Доступ к данным с помощью ADO.NET (C++/CLI)](/dotnet/data-access-using-adonet-cpp-cli.md) и [Доступ к данным в Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio).

<ul class="panelContent cardsF">
<li>
        <a href="/azure/sql-database/sql-database-develop-cplusplus-simple">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/azure/media/index/SQLDatabase.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Подключение к базе данных SQL с помощью C и C++</h3>
                        <p>Подключение к базе данных SQL Azure из приложений C или C++</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://github.com/Azure/azure-storage-cpp">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/azure/media/index/Storage.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Клиентская библиотека хранилища Microsoft Azure для C++</h3>
                        <p>[Хранилище Azure](/azure/storage/storage-introduction) представляет собой решение облачного хранилища для современных приложений, которым необходима устойчивость, доступность и масштабируемость для удовлетворения потребностей пользователей. Подключитесь к хранилищу Azure из приложения на языке C++ с помощью клиентской библиотеки хранилища Azure для C++.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_drivers.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Драйвер ODBC 13.1 для SQL Server — выпуск для Windows</h3>
                        <p>Последняя версия драйвера ODBC обеспечивает надежный доступ к базам данных SQL Microsoft Azure и Microsoft SQL Server 2016 для приложений на языках C и C++. Предоставляет поддержку таких функций, как Always Encrypted, Azure Active Directory и группы доступности AlwaysOn. Также доступен для MacOS и Linux.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://msdn.microsoft.com/library/ms130892.aspx">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_api.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Собственный клиент SQL Server</h3>
                        <p>Собственный клиент SQL Server — прикладной программный интерфейс (API) для автономного доступа к данным, который используется для OLE DB и ODBC и поддерживается в версиях SQL Server начиная с SQL Server 2005 и заканчивая SQL Server 2014. В новых приложениях следует использовать драйвер ODBC версии 13.1 для SQL Server.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/cpp/data/data-access-programming-mfc-atl">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_api.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Программирование доступа к данным</h3>
                        <p>Описывает программирование доступа к данным прежних версий с помощью Visual C++, когда предпочтительным способом является использование одной из библиотек классов, например Active Template Class Library (ATL), или библиотеки Microsoft Foundation Class (MFC), которые упрощают работу с API базы данных.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/cpp/data/odbc/open-database-connectivity-odbc">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_multi-connect.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Интерфейс ODBC (ODBC)</h3>
                        <p>Библиотека Microsoft Foundation Classes (MFC) предоставляет классы для разработки программ с использованием интерфейса ODBC.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="/cpp/data/oledb/ole-db-programming">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardImageOuter">
                        <div class="cardImage">
                            <img src="/media/common/i_generic-database.svg" alt="" />
                        </div>
                    </div>
                    <div class="cardText">
                        <h3>Программирование объектов OLE DB</h3>
                        <p>Ссылки на разделы, посвященные технологии баз данных OLE DB и библиотеке шаблонов OLE DB. (OLE DB не рекомендуется использовать в новых приложениях, за исключением сценариев, включающих связанные серверы.)</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    
</ul>

---

<h2>Ссылка</h2>

<ul class="panelContent cardsW">
 <li>
        <a href="https://azure.microsoft.com/develop/cpp/">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Центр разработчиков C и C++ для Microsoft Azure</h3>
                        <p>Azure позволяет легко создавать приложения C++, обладающие высокой гибкостью, масштабируемостью и надежностью, с помощью тех инструментов, которые вам нравятся.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Использование хранилища BLOB-объектов в программах на C++</h3>
                        <p>Хранилище BLOB-объектов Azure — это служба, которая сохраняет неструктурированные данные в облаке в виде BLOB-объектов. В хранилище BLOB-объектов можно хранить любые типы текстовых или двоичных данных, таких как документы, файлы мультимедиа или установщики приложений. Хранилище BLOB-объектов также называют хранилищем объектов.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <a href="https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference">
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3>Справочник программиста по ODBC</h3>
                        <p>Интерфейс ODBC предназначен для использования с языком программирования C. Использование интерфейса ODBC охватывает три области: инструкции SQL, вызовы функций ODBC и программирование на языке C.</p>
                    </div>
                </div>
            </div>
        </div>
        </a>
    </li>
    <li>
        <div class="cardSize">
            <div class="cardPadding">
                <div class="card">
                    <div class="cardText">
                        <h3><a href="https://www.microsoft.com/download/details.aspx?id=53339" title="Microsoft® ODBC Driver 13.1 for SQL Server® - Windows Download Page">Драйвер JDBC 13.1 для SQL Server</a></h3>
                    </div>
                </div>
            </div>
        </div>        
    </li>
    
</ul>
